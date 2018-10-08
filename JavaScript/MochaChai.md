# Mocha and Chai
## Installation
If you don't have node initialized install it
```
npm init
```
install mocha
```
npm i mocha --save
```
install chai
```
npm i chai --save
```
make sure your package.json test is set to mocha
```
"scripts": {
  "test": "mocha"
},
```

## File setup
Mocha reads test files that end in Test.js. Under that convention file names should look like this:
- index.js - code you are testing
- indexTest.js - tests


## Mocha
A JavaScript test framework that can be run on Node.js or in the browser
- describe - wraps a grouping of tests
- it - defines a test case
- before - execute before running tests
- beforeEach - execute after each test case
- after - execute after running tests
- afterEach - execute before each test case
- error - set test to error
