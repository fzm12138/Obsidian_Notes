### Multithreading 
- Assigns multiple code segments to a signle process
- Code segements are referred to as *threads*
- These *threads* shares the same memory space whthin a parent process
	- *Saves system memory*
	- *Increase computer speed and improves app performance*
eg:
- Multi tabs of a browser is *threads*
- CloudMusic and browser is *processes*

### Multiprocessing
- Refers to a system that has multi-running parallel processings

#### MultiThreading vs. MultiProcessing
- ***Multiprocessing*** uses 2 or more CPUs to increase coputing power
	- *MultiThreading* usese a single process with multiple code segments
- ***MultiProcessing*** increases CPUs to increase computing
	- *MultiThreading* focuses on generating computing threads from a single process 
- ***MultiProcessing*** is used to create a reliable system
	- *MultiThreading* is used to create threads that run parallel to each other
- ***MultiProcessing***  requires a significatn amount of time and specfic resources to create
	- *MutltiThreading* is quick to create and requires few resources
- ***MultiProcessing*** executes many oricesses simultaneously
	- *MutiThreading* excutes many threads simultanesously
- ***MultiProcessing*** creates a separate address space for each process
	- *MultiThreading* uses a common address space

##### Benefits of multiThreading 
- less memory storage
- Same parent process makes accessing memory easier
- Threads switching is fast and efficient
- Generate new thread within an existing process (Faster)
- All threads are lightweight and have lower overhead
- The cost of communication between threads is relatively low
- Creating responsive user interfaces is easy
##### Drawbacks of multiThreading
- A multiThreading system can't be interrupted
- the code could be hard to understand
- The overhead associated with managing different threads might be too costly for basic tasks
- Debugging and troubleshooting issues may be hard

##### Benefits of multiPorcessing 
- Code is simple
- *Child processes* could be interrupted
- Completes tasks faster and analyzes large amouts of data
- Uses multi CPUs to improve systems overall power
- Removes synchronization primitives
##### Drawbacks of multiProcesssing
- Requites more memory storage and overhead than threads to move data between processes
- Spawning processing takes longer than spawning threads
- An inter-process communitcation model must be implemented to share objs between processes
- The entire memory is copied into each subporcesses cause more overhead

## Tips for choosing between them
1. Use *multiThreading* to make user interatction programs resonsive 
2. Use *multiThreading* to creat ***I/O-bound*** or ***network-bound*** apps
3. Use **multiprocessing** to create ***computation-intensive*** apps
4. Use **multiprocessing** to develop programs that are ***CPU intensive***





















