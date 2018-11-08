# Jest
A JavaScript testing framework, runner, and assertion library by Facebook. It comes with create-react-app so there is no need to install if you are using React.

## Getting Started
Import react and the file you are testing. You can use the describe, it framework to set up your tests and expect to setup your comparison.

```
import React from 'react'
import manageBand from './manageBand'
describe('manageBand', ()=> {
  it('no bands have been added', ()=>{
    let action = {type:'@@INIT'}
    expect(manageBand(undefined, action)).toEqual({"bands": []})
  })
})
```

## Matchers

* Common Matchers
  - toBe - what you expect it to be - used to look for a specific value
  - toEqual - recursively checks every field of an object or array

* Truthiness
  - toBeNull - matches only null
  - toBeUndefined - matches only undefined
  - toBeDefined - is the opposite of toBeUndefined
  - toBeTruthy - matches anything that an if statement treats as true
  - toBeFalsy - matches anything that an if statement treats as false

* Numbers
  - toBeGreaterThan/ toBeLessThan
  - toBeGreaterThanOrEqual
  - toBeCloseTo - to account for rounding errors

* Strings
  - toMatch/ .not.toMatch

* Arrays
  - toContain

* Exceptions
  - toThrow - error


## Snapshot Testing

Snapshot testing on the first time run takes a snapshot of your code and saves it to a snapshot folder that it creates. The next time you run the test the code will compare the snapshot to the current code and fail if there has been a change and articulate that change.

### Set up for snapshot testing a static component
For React you will need a package called react-test-renderer.

```
npm i react-test-renderer
```

You will need to require React, react-test-renderer, and the file you would like to snapshot test.

```
import React from 'react';
import Header from './Header'
import renderer from 'react-test-renderer'

```

Set up your tests with the describe, it syntax.

```
describe('Header', ()=>{
  it('renders correctly', () => {

  });
})
```
Then use react renderer to generate a serializable value for your React tree.

```
const tree = renderer
      .create(<Header />)
      .toJSON();
```

Expect calls the function that you are testing and in this case we are passing in the tree. Then we will use the matcher .toMatchSnapshot().

```
describe('Header', ()=>{
  it('renders correctly', () => {
    const tree = renderer
      .create(<Header />)
      .toJSON();
    expect(tree).toMatchSnapshot();
  });
})
```
