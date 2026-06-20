# Operating Systems: CPU Scheduling Algorithms

This repository contains implementations and explanations of various CPU scheduling algorithms used in modern operating systems. CPU scheduling is the process that allows one process to use the CPU while the execution of another process is on hold (in a waiting state) due to the unavailability of any resource like I/O etc., thereby making full use of the CPU.

## Algorithms Implemented

### 1. Round Robin (RR)
**Round Robin** is a preemptive CPU scheduling algorithm where each process is assigned a fixed time slot (known as a **time quantum** or **time slice**) in a cyclic way. 

* **How it works:** The scheduler goes through the ready queue, allocating the CPU to each process for a time interval of up to 1 time quantum. If the process's burst time is less than the time quantum, the process releases the CPU voluntarily. If it exceeds the time quantum, the process is preempted and put back at the end of the ready queue.
* **Key Feature:** Fair allocation of CPU, prevents starvation, but performance heavily depends on the choice of the time quantum.

### 2. Shortest Job First (SJF)
**Shortest Job First (SJF)**, also known as *Shortest Job Next (SJN)*, is a scheduling policy that selects the waiting process with the smallest execution (burst) time to execute next.

* **How it works:** When the CPU becomes available, it is assigned to the process that has the smallest next CPU burst. If two processes have the same length CPU burst, FCFS (First-Come, First-Served) scheduling is used to break the tie.
* **Key Feature:** It is optimal because it gives the minimum average waiting time for a given set of processes. However, it can lead to **starvation** for longer processes if shorter jobs keep arriving continuously.
* **Variations:** Can be either **Non-preemptive** or **Preemptive** (Shortest Remaining Time First - SRTF).
