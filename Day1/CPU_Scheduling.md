# CPU Scheduling

## What is CPU Scheduling?

**CPU Scheduling** is the process by which the Operating System decides **which process gets access to the CPU** and for how long.

Since multiple processes may be ready at the same time, the OS uses a **CPU Scheduler** to manage CPU time efficiently.

---

## CPU Scheduler

The **CPU Scheduler**:
- Selects a process from the **Ready Queue**
- Allocates the CPU to the selected process
- Performs context switching when required

---

## Preemptive vs Non-Preemptive Scheduling

### Non-Preemptive Scheduling
- Once a process gets the CPU, it runs until completion or blocks for I/O
- Simple but may cause poor response time

### Preemptive Scheduling
- CPU can be taken away from a running process
- Better responsiveness
- Requires context switching

---

## Scheduling Criteria

A good CPU scheduling algorithm aims to:

- Maximize CPU utilization
- Maximize throughput
- Minimize turnaround time
- Minimize waiting time
- Minimize response time
- Ensure fairness

---

## Common CPU Scheduling Algorithms

### 1. First Come First Serve (FCFS)
- Processes are scheduled in arrival order
- Simple to implement
- May cause **convoy effect**

---

### 2. Shortest Job First (SJF)
- Process with shortest CPU burst is scheduled first
- Optimal for minimum average waiting time
- Can cause starvation

---

### 3. Priority Scheduling
- Processes scheduled based on priority
- Higher priority → executed first
- Starvation possible (solved using aging)

---

### 4. Round Robin (RR)
- Each process gets fixed time slice (time quantum)
- Cyclic scheduling
- Widely used in time-sharing systems

---

## Dispatcher

The **Dispatcher**:
- Switches context
- Switches to user mode
- Starts execution of selected process

---

## Multilevel Queue Scheduling

- Ready queue divided into multiple queues
- Each queue has its own scheduling algorithm
- Fixed priority between queues

---

## Summary

- CPU scheduling determines process execution order
- Scheduler selects processes from ready queue
- Algorithms aim to optimize performance metrics
- Preemptive scheduling improves responsiveness

---
