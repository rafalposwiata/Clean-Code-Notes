# Concurrency

### Basic definitions

- Bound Resources 

  Resources of a fixed size or number used in a concurrent environment. Examples include database connections and fixed-size read/write buffers.

- Mutual Exclusion 

  Only one thread can access shared data or a shared resource at a time.

- Starvation 

  One thread or a group of threads is prohibited from proceeding for an excessively long time or forever. For example, always letting fast-running threads through first could starve out longer running threads if there is no end to the fast-running threads.

- Deadlock 

  Two or more threads waiting for each other to finish. Each thread has a resource that the other thread requires and neither can finish until it gets the other resource.

- Livelock 

  Threads in lockstep, each trying to do work but finding another “in the way.” Due to resonance, threads continue trying to make progress but are unable to for an excessively long time or forever.
  
### Recommendations

- Keep your concurrency-related code separate from other code.

- Severely limit the access of any data that may be shared.

- Attempt to partition data into independent subsets than can be operated on by independent threads, possibly in different processors.

- Review the classes available to you. In the case of Java, become familiar with java.util.concurrent, java.util.concurrent.atomic, java.util.concurrent.locks

- Keep your synchronized sections as small as possible.

- Think about shut-down early and get it working early. It’s going to take longer than you expect.

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

### Deadlock

Two or more threads waiting for each other to finish. Each thread has a resource that the other thread requires and neither can finish until it gets the other resource. To really solve the problem of deadlock, we need to understand what causes it. There are four conditions required for deadlock to occur:

- Mutual exclusion

  Mutual exclusion occurs when multiple threads need to use the same resources and those resources can not be used by multiple threads at the same time or are limited in number. One strategy for avoiding deadlock is to sidestep the mutual exclusion condition. You might be able to do this by:
  
  - Using resources that allow simultaneous use, for example, AtomicInteger.
  
  - Increasing the number of resources such that it equals or exceeds the number of competing threads.
  
  - Checking that all your resources are free before seizing any.

- Lock & wait

  Once a thread acquires a resource, it will not release the resource until it has acquired all of the other resources it requires and has completed its work. You can eliminate this by refuse to wait. Check each resource before you seize it, and release all resources and start over if you run into one that’s busy. This approach can cause problems like Starvation or Livelock.

- No preemption

  One thread cannot take resources away from another thread. Once a thread holds a resource, the only way for another thread to get it is for the holding thread to release it. Strategy for avoiding deadlock is to allow threads to take resources away from other threads. When a thread discovers that a resource is busy, it asks the owner to release it. If the owner is also waiting for some other resource, it releases them all and starts over.
  
- Circular wait

  This is also referred to as the deadly embrace. Imagine two threads, T1 and T2, and two resources, R1 and R2. T1 has R1, T2 has R2. T1 also requires R2, and T2 also requires R1. Solution: if all threads can agree on a global ordering of resources and if they all allocate resources in that order, then deadlock is impossible.

### Testing Multithreaded Code

Recommendations for testing multithreaded Code:

- Treat spurious failures as candidate threading issues.

  Do not ignore system failures as one-offs.

- Get your nonthreaded code working first.

  Do not try to chase down nonthreading bugs and threading bugs at the same time. Make sure your code works outside of threads.

- Make your threaded code pluggable.

  Make your thread-based code especially pluggable so that you can run it in various configurations.

- Make your threaded code tunable.

  Allow the number of threads to be easily tuned. Consider allowing self-tuning based on throughput and system utilization.

- Run with more threads than processors.

- Run on different platforms.

  Run your threaded code on all target platforms early and often.

- Instrument your code to try and force failures.

  There are two options for code instrumentation: hand-coded and automated.
