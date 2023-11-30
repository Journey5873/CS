# What is Process?
“Process is a program in execution”

### Process context
Process context is CPU’s current status.  
<img src="https://github.com/Journey5873/CS/assets/99030586/cd042f66-7d6f-4f91-a3b8-3ffe70985e97" height="400">

This a concept used to indicate what a program has done, how far it has progressed.
👉 When a process is allowed CPU time, the PC (program counter register) points the code that should be excuted.
It reads the instruction from the code, inputs the value into register, and perfirns calculations in ALU.
After that, it stores the result in either a register or memory.

Process context needs to determine the progress of a process at a given point in time.

#### To understand **Process context**, you need to have information about...

✅ Hardware context → the hardware context related to the CPU.
- Program Counter
- Register (values stored in registers)

✅ Process address space
- code, data, stack
<img src="https://github.com/Journey5873/CS/assets/99030586/d4821835-7d03-4fa8-9a96-ad6873d1851d" height="300">

✅ process kernel data structure

- PCB (Process Control Block)
- Kernel stack
    Each process has own kernel stacks

# Process State

→ This is how the OS divides the user process state for management.<br>
When a process works, it changes its state.

<img src="https://github.com/Journey5873/CS/assets/99030586/4190c0d3-37e6-4577-b580-8dd79fabb2a8" height="300">

1. Running
    - The process is executing instructions with the CPU.
2. Ready (In memory)
    - The process is waiting for the CPU.
    - It has to satisfy all the conditions, such as memory requirements. It is ready to be executed as soon as it gets the CPU.
        
        (Everingthing has to be in memory to execute program in CPU.)
        
3. Waiting (blocked, sleep)
    - The process can't execute instructions even thoght it gets the CPU.
    - Process is waiting because the tasks that it has requested such as events  events (e.g., I/O), haven't been satisfied immediately.
  
        All of the program's memory doesn't in the physical memory (because the memory is limiated). If the code that needs to be executed is not in the memory but is instead
        on secondary storage, the CPU cannot immediately execute instructions, even if it is is allocated.
        
4. Suspended (stopped)
    - The process is forcefully stopped from outside.
      
        → e.g., There are too many processes in memory, and some are swapped out by the Medium-term Scheduler.
        
    - The entirety of the process's memory is swapped out to disk.
5. New
    
    The process is currently being created.
    
6. Terminated
    
    Execution is complete.
    

⭐ Blocked: The process can transition to the ready state when the tasks it has requested are satisfied.

⭐ Suspended: The process should be resumed from outside.

---

# Process Control Block (PCB)

<img src="https://github.com/Journey5873/CS/assets/99030586/66157669-bef6-488f-8b73-d2967a722583" height="300">

A Process Control Block in OS (PCB) is **a data structure used by the operating system to manage information about a process**. 

→ To manage each process, the OS relies on this information maintained individually by each process.

(1) Information managed by OS

- Process state(Ready, Running, Waiting), Process ID
- Scheduling information, Priority
    
    Allocating CPU based on the process priority.
    

(2) Hardware values related to CPU execution

- Program counter, registers
    
    Hardware-related information to understand the process context.
    
    (Which register values were in the CPU for execution)
    

(3) Memory-related information:

- code, data, stack location details
    
    Information about the address space for the process context.
    

(4) Open file descriptors

- Open file descriptors …

---

# Context Switch

A context switch refers to the process of saving the current state (context) of a running process, so that it can be later restored and resumed, while switching to another process to execute.

→ The process of transferring the CPU from one process to another.

### Test involved in a context switch:

When the CPU needs to be handed over to another process, the value stored in the register and PC(Program Counter), memory map are saved in PCB.

To resume another process that has CPU again, OS rerieves the context from the PCB and restores it to the hardware.

❗It doesn't mean a system call or interrupt always occurs the context switch.

It happens during the transition from process A ➡️ process B, where the CPU moves from one user process to another.

If a system call or interrupt occurs, transitioning from process A ➡️ OS (The CPU moves from a user process to the OS)

<img src="https://github.com/Journey5873/CS/assets/99030586/03b34b41-a08f-43dd-8d63-c596ea06aaa8" height="200" width="700">

<img src="https://github.com/Journey5873/CS/assets/99030586/2c3895c6-bb20-4eec-a274-03aa8b52735d" height="200" width="700">

---

# Scheduler

1. Long-term Scheduler (Job scheduler)
    - Determines which process to allocate memory to.
    - Decides which starting process moves to the ready queue.
        
        → Decides whether to allocate memory or not when transitioning from the New state to the Ready state (at the start of a program).
        
    - degree of Multiprogramming control
        
        Controls the number of process in memory.
        
        Either too many or too few programs in memory can adversely affect performance.
        
    - Time-sharing systems usually don't have a Long-term Scheduler (all processes are in the ready state by default).
  
2. Short-term Scheduler (CPU scheduler)
    - Determines which process to allocate the CPU to. → Decides which process to run.
    - Operates in milliseconds.
3. Medium-term Scheduler (Swapper) 
    - Swaps out entire processes from memory to disk to free up space.

        Initially, all processes are loaded into memory.
        
    - Addresses issues of taking away memory from a process
    - **degree of Multiprogramming control**

---

## User Program’s process state diagram

<img src="https://github.com/Journey5873/CS/assets/99030586/925d1080-62e5-468a-82f0-69a123c4539e" height="300">

User mode Running: The process holds the CPU and executes its code.

Monitor mode Running: Invoking a system call to execute the operating system's code.

→ The process is Running in kernel mode ⭕, while the OS is Running ❌.

---

# Thread

A thread (or lightweight process) is a basic unit of CPU utilization.<br>
There are multiple units of CPU execution within a single process.

<img src="https://github.com/Journey5873/CS/assets/99030586/9d52c0af-c528-495a-a4f4-2bd63caff3d0" height="300">

Composition of a Thread (independently held components):

- program counter
- register set
- stack space

Components shared among threads (common task):

- code section
- data section
- OS resources

Pros

1. When one thread is in a waiting satus, another thread can be allocated the CPU and for execution. It make it posibble faster processing.
    
    ex) When reading a web page, if one thread is blocked (e.g., for network operations), another thread can continue processing (e.g., displaying content).
    
3. Creating separate processes for the same task results in resource wastage.

<img src="https://github.com/Journey5873/CS/assets/99030586/155af85f-9f71-4fd1-a5af-61421812979a" height="300">


# Benefits of Threads

1. Responsiveness
    
    eg) multi-threaded Web 
    
    if one thread is blocked(eg network) another thread continues(eg display)
    
2. Resource Sharing
    
    N threads can share binary code, data, resource of the process
    
3. Economy
    
    creating & CPU switching thread (rather than a process)
    
    → Creating a new process involves significant overhead.
    
    → Context switching between processes involves substantial overhead (e.g., saving CPU-related information, flushing the cache memory). In contrast, CPU switches between threads within the same process are relatively straightforward.
