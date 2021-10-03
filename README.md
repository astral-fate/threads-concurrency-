# threads-concurrency

Threads & Concurrency:

CHAPTER OBJECTIVES 
• Identify the basic components of a thread, and contrast threads and processes.
 • Describe the major benefits and significant challenges of designing multithreaded processes. 
• Illustrate different approaches to implicit threading, including thread pools, fork-join, and Grand Central Dispatch.
 • Describe how the Windows and Linux operating systems represent threads. 
• Design multithreaded applications using the Pthreads, Java, and Windows threading APIs.



single-threaded process and a multithreaded process/ If a process has multiple threads of control, it can perform more than one task at a time.

Multicore/ more computing performance, single-CPU systems evolved into multi-CPU systems.

Data parallelism/ focuses on distributing subsets of the same data across multiple computing cores and performing the same operation on each core.

Task parallelism/ involves distributing not data but tasks (threads) across multiple computing cores.

user threads/ support for threads may be provided either at the user level kernel threads

Green threads/ —a thread library available for Solaris systems and adopted in early versions of Java—used the many-to one model.

two-level model/ any-to-many model still multiplexes many user level threads to a smaller or equal number of kernel threads but also allows a user-level thread to be bound to a kernel thread.

A thread library/ provides the programmer with an API for creating and man aging threads


wo general strategies for creating multiple threads:

asynchronous threading/asynchronous threading, once the parent creates a child thread, the parent resumes its execution, so that the parent and child execute concurrently and independently of one another. Because the threads are independent, there is typically little data sharing between them

synchronous threading/ Asynchronous threading is the strategy used in the multithreaded server

Pthreads/ refers to the POSIX standard (IEEE 1003.1c) defining an API for thread creation and synchronization.

Closures/ Lambda expressions— as well as similar functions

implicit threading/ One way to address these difficulties and better support the design of con current and parallel applications is to transfer the creation and management of threading from application developers to compilers and run-time libraries.

thread pool/ Unlimited threads could exhaust system resources, such as CPU time or memory. One solution to this problem is to use a thread pool

fork-join model/ the strategy for thread creation

parallel regions/ OpenMP identifies parallel regions as blocks of code that may run in parallel.

a dispatch queue/ GCD schedules tasks for run-time execution by placing them

main queue/ when a task has been removed from the queue, it must complete execution before another task is removed. Each process has its own serial queue

user-interactive/ class represents tasks that interact with the user, such as the user interface and event handling, to ensure a responsive user interface. Completing a task belonging to this class should require only a small amount of work.

user-initiated/ QOS CLASS USER INITIATED—The user-initiated class is similar to the user-interactive class in that tasks are associated with a responsive user interface; however, user-initiated tasks may require longer processing time.

Utility/ class represents tasks that require a longer time to complete but do not demand immediate results. This class includes work such as importing data

Background/ class are not visible to the user and are not time sensitive. Examples include indexing a mailbox system and performing backups.


Block/ for the C, C++, and Objective-C languages, GCD identifies a language extension known block


iteration space/ where range refers to the range of elements that will be iterated (known as the iteration space) and body specifies an operation that will be performed on a subrange of elements. 

Signal/ l is used in UNIX systems to notify a process that a particular event has occurred


default signal handler/

user-define signal handler/

 asynchronous procedure calls (APCs)/





target thread/ A thread that is to be canceled is often referred to as the target thread. Cancellation of a target thread may occur in two different scenarios

cancellation point/ occurs only when a thread reaches a cancellation poin

cleanup handler/ Pthreads allows a function

thread-local storage (or TLS)/ in some circumstances, each thread might need its own copy of certain data. We will call such data



lightweight process/ Many systems implementing either the many-to-many or the two-level model place an intermediate data structure between the user and kernel threads

scheduler activation/ One scheme for communication between the user-thread library and the kernel

upcall/ the kernel provides an application with a set of virtual processors (LWPs), and the application can schedule user threads onto an available virtual processor. Furthermore, the kernel must inform an application about certain events

upcall handler/ This procedure is known as an upcall. Upcalls are handled by the thread library with an upcall


 context/ The register set, stacks, and private storage area are known as the context of the thread.




