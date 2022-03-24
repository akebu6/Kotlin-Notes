# Call Stack or Execution Stack Structure
> is composed of stack frames that store information about functions that have not yet terminated.
- The information includes the return address of a function, parameters, local variables, intermediate computations, and some other data.
- the call stack follows the rule Last In First Out (LIFO).
- A new stack frame is added when the execution enters the new function.
- And the stack frame is removed from the call stack if the execution of a function is done.
- Actually, the stack stores just a reference to the args array since all reference types are stored in heap memory. But, the stack stores the actual value of n.
- The number of possible function invocations depends on the amount of memory allocated to the stack. When your stack contains too many stack frames, it can be overflowed. It leads to the StackOverflowError that will stop the execution.
- The stack size can be set with the command line option -Xss for executing a particular program
