---
Created: 2022-03-30T08:33
---
Học background software engineer.

- Scheduling
    
    **2 Objectives:**  
    - Multiprogramming: switch between processes when the CPU is idle.  
    - TimeSharing: switch between processes frequently enabling the interaction of users over multi programs.  
    → To achieve those objectives, process scheduling will choose the available process (from a set of available processes) to run on the CPU.**Queue:**  
    - Job queue: when a process enters the system, they will be in the job queue, where contain all processes, initializing.  
    - Ready queue: process residing in main memory and waiting for execution.  
    - Blocked Queue :  
    List of processes waiting for I/O  
    - When a new process is created it stays in the job queue and if is ready for execution it then moves to ready queue
    
- PCB (Process Control Block)
    
    Each process is represented in the OS by PCB.  
    Properties:  
    - Process state: running, idle, pending, stop.  
    - Process number: Process id.  
    - Program counter: which line of code is executed.  
    - Register: data holding places that are part of the CPU. A register may hold an instruction, a storage address, or other kinds of data needed by the process
    
- Thread vs Process
    
    - Process is a program in execution, thread is a unit of execution within a process.  
    - Each process is started with a single thread, often called the primary thread.  
    - The process has its **own stack, memory, and data** || Threads **share the same memory.** They do, however, have their **own stack.**  
    - On a multiprocessor system, **multiple threads can concurrently run on multiple CPUs**  
    - Copies of the stack and the heap are made for the newly created process by fork.
    
- Thread
    
    - Comprise Thread ID, program counter, register set, and stack.  
    Thread shares code section, data section, open files, and signals.  
    - Benefits:  
    + Responsive: multi-thread doing multiple tasks.  
    + Resource sharing: Allow an application to have several different threads of activity within the same address space.  
    + Economy: Allocating memory and resources for process creation is costly. Thread shared resources, it is more economical to create and context-switch thread.  
    + Utilization of multiprocessor architecture: Threads may be running in parallel on different processors.  
    - Threads are more vulnerable to problems caused by other threads in the same process.  
    - Register context (Program counter, processor status register, stack pointer, general-purpose  
    registers)  
    _Thread-safe_ means that an object can be used by many threads concurrently and still be correct 1._Thread hostile_ means that the object does something (mutates static state, thread-local storage, etc.) that prevents it from being thread-safe._Thread compatible_ means not _thread-safe_, but not _thread hostile_ - so to satisfy thread safety, the user must perform synchronization themselves.
    
    ![[Untitled 2.png|Untitled 2.png]]
    
- Race condition
    
      
    
- Interprocess Communication
    
    **Shared memory**:  
    - Definition: a region of memory is shared among processes (read/write).  
    - Steps:  
    + Process A creates a shared memory segment that reside the address space of A.  
    + Process A removes the restriction about “Prevent other processes access the A’s memory”.  
    + Process B attaches A’s shared memory segment.  
    - Ex:  
    + Pipe: one-way communication only i.e we can use a pipe such that One process writes to the pipe, and the other process reads from the pipe. It opens a pipe, which is an area of main memory that is treated as a _**“virtual file”**_.  
    If a process tries to read before something is written to the pipe, the process is suspended until something is written.**Message passing:**  
    - Definition: Process A sends a message to Kernel. Kernel will redirect it to process B.  
    Usefull when processes in different computers.  
    - Send/Receive:  
    + Fixed size: easy system-level implement / Hard programming task.  
    + Variable size: hard system-level implement / Simpler programming task.  
      
    
- context switch
    
    Definition:  
    - Context switching of thread is faster than process → thread is executed faster.  
    the context switch is the process of storing the state of a [process](https://en.wikipedia.org/wiki/Process_\(computing\)) or [thread](https://en.wikipedia.org/wiki/Thread_\(computing\)) so that it can be restored and resume [execution](https://en.wikipedia.org/wiki/Execution_\(computing\)) at a later point. This allows multiple processes to share a single [central processing unit](https://en.wikipedia.org/wiki/Central_processing_unit) (CPU)  
    - The context is represent in the PCB of the process.  
    Pros and Cons:  
    - When context switching is running, CPU is idle  
    Steps:  
    - Save the context of the process that is currently running on the CPU. Update the process control block and other important fields.  
    - Move the process control block of the above process into the relevant queue such as the ready queue, I/O queue, etc.  
    - Select a new process for execution.  
    - Update the process control block of the selected process. This includes updating the process state to running.  
    - Update the memory management data structures as required.  
    - Restore the context of the process that was previously running when it is loaded again on the processor. This is done by loading the previous values of the process control block and registers.**Triggers:** Interrupts, Multitasking, Kernel/User switch
    
- CPU Thread
    
    4 cores 8 threads → 8 CPU threads.  
    (Hyperthreading) Thực tế chỉ có 1 physical core nhưng có tới 2 virtual core. Khi nhân CPU rảnh (cache missing: đang load dữ liệu từ RAM), thì nó sẽ đc giao làm task khác. Do có 2 register độc lập chứa 2 task khác nhau.  
    Khi một thread được CPU xử lý đủ lâu, hệ điều hành sẽ tạm dừng việc xử lý thread này lại và đưa một thread kế tiếp trong hàng đợi cho CPU xử lý. Quá trình này diễn ra **đủ nhanh đến mức gây cho chúng ta** _**ảo giác**_ **rằng các tác vụ đang được chạy** _**song song**_
    
- Stack vs heap memory
    
    Stack:  
    - The allocation happens on contiguous blocks of memory.  
    - Named stack: the allocation happens in the function call stack.  
    - Manipulated (allocated/de-allocated) by the compiler.  
    Heap:  
    - The allocation happens on random blocks of memory.  
    - Manipulated (allocated/de-allocated) by the user.
    
- Socket
    
    - Used for communication for client/server systems.  
    - Each endpoint will deploy a socket to make the connection.  
    - Socket ID: IP + port.  
    - Server waits for incoming requests on a specified (well-known < 1024) port. Client will deploy a socket with IP + port (<1024) and send request to the server.
    
- TCP/IP vs UDP
    
    - TCP breaks each message into _packets_ with header included, and those packets are then reassembled on the other end.  
    Sequence number: order of packet.  
    Ack Number: Got it or dropped.  
    Checksum: Packet right or wrong.  
    - IP defines how to address and route packets for delivery.  
    - TCP: 3-way handshake.  
    - UDP: Voice call, online game, live, no handshake  
    - Port is in TCP, UDP header.  
    - Packet will go from Application → Transport → Network → Data Link in the sender and the receiver will unwrap the packet in the revert way (From Data Link → Application).
    
    ![[Untitled 1.png]]
    
- HTTP
    
    **HTTP request**:  
    - URL (Endpoint).  
    - Method: GET, HEAD, POST, PUT, DELETE.  
    - Headers: token, accept, content-type (XML, JSON).  
    - Body: data.**HTTP respond**:  
    - Status code.  
    - Headers: (key: value).  
    - Body
    
- Mutex lock vs semaphore
    
    ![[Untitled 2 2.png|Untitled 2 2.png]]
    
    Overcome waiting:  
    + Put waiting threads into a waiting queue → Release CPU utilization.  
    + If resource available → signal to this queue.  
    But this implement can cause a deadlock.
    
    ![[Untitled 3.png]]
    
- CPU bound / IO bound
    
    A program is CPU bound if it would go faster if the CPU were faster.  
    A program is I/O bound if it would go faster if the I/O subsystem was faster.  
    (IO can be disk reading, network, communication, ...)
    

[[Database]]