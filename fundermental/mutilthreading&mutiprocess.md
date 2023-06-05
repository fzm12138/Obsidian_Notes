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
- 