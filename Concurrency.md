# Concurrency

### Executor Framework

The Executor framework (from java.util.concurrent package) will pool threads, resize automatically, and recreate threads
if necessary. It also supports futures, a common concurrent programming construct and works with classes that implement Runnable or Callable interface.

### Nonblocking Solutions

Modern processors have an operation typically called Compare and Swap (CAS). This operation is analogous to optimistic locking in databases, whereas the synchronized version is analogous to pessimistic locking. Classes from package java.util.concurrent.atomic implement this solution.

### Nonthread-Safe Classes

There are some classes that are inherently not thread safe. Here are a few examples:

- SimpleDateFormat
- Database Connections
- Containers in java.util
- Servlets

### Dependencies Between Methods Can Break Concurrent Code

When your client code uses two methods which must be synchronized together then you have three options:

- Tolerate the failure.
- Solve the problem by changing the client: client-based locking
- Solve the problem by changing the server, which additionally changes the client: server-based locking
