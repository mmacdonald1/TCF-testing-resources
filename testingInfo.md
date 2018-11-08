# Testing

## Vocabulary
- Unit - a "unit of code" can be a single function, object, module, component etc.
- Unit tests - testing on a unit of code
- Integration tests - multiple units are tested as a group
- Regression testing - testing previous code and changes to determine that your code is still functional after a change
- Acceptance/ Functional tests- automatic testing of the entire application
- TDD - Test Driven Development - the process by which you write and run tests
  - steps of TDD
    1. Write a test
    2. Run the test and watch it fail
    3. Write the minimum amount of code to make the test pass
    4. Run the tests to check if new test passes
    5. Refactor
- BDD - Behavior Driven Development - best practices for writing tests used with TDD and Unit tests. Allows you to think of how code behaves as opposed to how it is implemented.


## Classfications of Testing Software

1. Test Runners
- runs your tests
- Karma - creates a fake server to test your code in multiple browsers

2. Testing Frameworks
- creates a set of rules and tools to create test cases
- Mocha - uses the describe and it structure to allow users to write test cases

3. Assertion Libraries
- plugs into a framework to determine if a condition is valid or not
- Chai - uses conditions like toEqual or exist to test if code meets a the defined condition

4. Testing Plugins
- programs that can be installed to add an additional feature on existing test software
- Sinon plugin includes spies, stubs, and mocks
  spy - a function that records arguments, return value, the value of this and exception thrown (if any) for all its calls
  stubs - functions (spies) with pre-programmed behavior
  mocks -  are fake methods (like spies) with pre-programmed behavior (like stubs) as well as pre-programmed expectations.
