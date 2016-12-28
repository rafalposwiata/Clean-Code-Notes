# Possible Paths of Execution

### Number of Paths

For simple case of N instructions in a sequence, no looping or conditionals, and T threads, the total number of possible execution paths is equal to:

<p align="center">
  <img src="/images/number-of-execution-paths.png"/>
</p>


### Definitions related with method invocation in Java

- Frame

  Every method invocation requires a frame. The frame includes the return address, any parameters passed into the method and the local variables defined in the method. This is a standard technique used to define a call stack, which is used by modern languages to allow for basic function/method invocation and to allow for recursive invocation.

- Local variable

  Any variables defined in the scope of the method. All nonstatic methods have at least one variable, this, which represents the current object, the object that received the most recent message (in the current thread), which caused the method invocation.

- Operand stack

  Many of the instructions in the Java Virtual Machine take parameters. The operand stack is where those parameters are put. The stack is a standard last-in, first-out (LIFO) data structure.
