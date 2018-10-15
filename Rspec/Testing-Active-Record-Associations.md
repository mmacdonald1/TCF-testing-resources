# The problem

Our laps frequently want students to establish ActiveRecord relationships in a particular way. I was struggling to find a way to test that didn't involve manually calling the methods that should be created by each association. This was a sloppy way of going about it and didn't actually ensure that students had not manually created an ORM or something ridiculous.

# Solution

Turns that there's a super simple way to do it. ActiveRecord provides a class method [reflect_on_association](https://api.rubyonrails.org/classes/ActiveRecord/Reflection/ClassMethods.html#method-i-reflect_on_association) which returns an AssociationReflection. Then we can use `AssociationReflection#macro` to compare agains a symbol:

```
expect(Artist.reflect_on_association(:songs).macro).to eq(:has_many)
```
