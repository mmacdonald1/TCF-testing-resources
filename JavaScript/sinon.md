# Sinon

A plugin that replaces calls to the server with calls to a fake server.

## Spies
Allows you to check if the function is called and check the parameters that it is called with.

.called - true if the spy was called at least once
.calledWith - true if the spy was called at least once with the provided arguments
.threw - true if spy threw an exception at least once
.returned - true if spy returned the provided at least once


## Stubs
Spies that force a certain result
```
let foo = sinon.stub()
foo.returns(true)
someFunction(foo).should.be.true
```
## Mocks
Are fake methods (like spies) and have pre-programmed behavior (like stubs), but they also have pre-programmed expectations. Overall it checks if a function is used exactly how we expect it to be.
