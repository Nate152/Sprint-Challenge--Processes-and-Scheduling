1. List all of the main states a process may be in at any point in time on a
   standard Unix system. Briefly explain what each of these states mean.

   The main states for a standard Unix system are I, R, S, T, U and Z. I means an idle state where the process has been sleeping for approximately 20 seconds. R is a runnable process that has been intiated and is ready to be run. S is a sleeping process that has been idle for less than 20 seconds. T is a stopped process that can be restarted. U is an uninterruptible wait meaning the process is waiting for communication from some piece of hardware. Z is a zombie process that is not running but has not yet been cleaned up by the system and is therefore still viewable on the process table.

2. What is a Zombie Process? How does it get created? How does it get destroyed?

   A zombie process is one that has been terminated by the OS but is still viewable in the process table because it has not been cleaned up by the system. These are created when a child process is ended but it has to wait on an exit status to be read by its parent via the wait system call. Once this status is read by the parent, it is removed.

3. Describe the job of the Scheduler in the OS in general.

   The job of the scheduler is to allocate processor resources appropriately in order for the computer to function. A CPU is limited by the number of cores it contains and can only run so many processes at a given time. The scheduler determines which processes should be executed in what order based on a number of variables such as order received, response time, and completion time. Many schedulers use multi-level feedback queues to organize processes and ensure maximum efficiency of the CPU.

4. Describe the benefits of the MLFQ over a plain Round-Robin scheduler.

   A round robin scheduler simply runs each process that comes in for a given amount of time and if it is not complete it gets moved to the back of the line. Each process gets the same amount of time to run whether it takes 5 ns or 100 ns. A MLFQ allows the scheduler to organize the processes by runtime and organize them into queues according to the time it will take for the process to complete. This means that very fast processes will get completed first and longer ones will be moved down the queues and given the appropriate amount of time to complete. The MLFQ method tends to be much more efficient for dealing with large amounts of processes.