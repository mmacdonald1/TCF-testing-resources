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
