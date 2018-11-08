# The Problem 

Floating point numbers are tricker to represent in memory and may be stored with different levels of precision. This can cause a problem if you try to test a floating point value using the `eq` matcher. The test could fail simply because the a [BigDecimal](https://ruby-doc.org/stdlib-2.5.1/libdoc/bigdecimal/rdoc/BigDecimal.html) instead of a [Float](https://ruby-doc.org/core-2.5.1/Float.html) or vice versa. This can especially be a problem when writting tests for ActiveRecord models which really just transfering a result obtained from some SQL implementation, whose floating-poit precision is unkown.

# The Solution 

Instead use the `be_within` matcher when testing floating-point return values. This matcher lets you specify the amount of precision that actually matters. For example, when I was writting ActiveRecord tests, the following kept failing:

```
    describe 'Dish.average_tag_count' do
      it 'returns the average tag count for all dishes' do
        total_tags = @dish_hash.reduce(0) do |sum, (dish, tags)|
          sum += tags.length
        end
        expected = total_tags.to_f / @dish_hash.keys.count.to_f
        expect(Dish.average_tag_count).to eq.of(expected)
      end
    end
```
but this one passed:

```
    describe 'Dish.average_tag_count' do
      it 'returns the average tag count for all dishes' do
        total_tags = @dish_hash.reduce(0) do |sum, (dish, tags)|
          sum += tags.length
        end
        expected = total_tags.to_f / @dish_hash.keys.count.to_f
        expect(Dish.average_tag_count).to be_within(1e-12).of(expected)
      end
    end
```
