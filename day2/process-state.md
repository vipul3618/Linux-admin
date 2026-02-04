# Five-State Process Model

The **five-state process model** is a classic operating system model used to describe the different states a process goes through during its **lifecycle**. It helps in understanding **process scheduling**, **resource allocation**, and **state transitions** managed by the operating system.

---

## Process States

### 1. **New**
- The process is **being created**.
- The operating system allocates initial resources and creates the **Process Control Block (PCB)**.
- The process is not yet ready to execute.
- Example: When a user launches a program, the OS begins setting up the process.

---

### 2. **Ready**
- The process has all required resources **except the CPU**.
- It is waiting in the **ready queue** to be scheduled.
- Multiple processes can be in the ready state simultaneously.
- The process is prepared to execute as soon as the CPU is assigned.

---

### 3. **Running**
- The process is currently being executed by the CPU.
- On a **single-core system**, only one process can be in this state at a time.
- On a **multi-core system**, multiple processes can run concurrently (one per core).
- The process actively performs instructions defined in its program.

---

### 4. **Blocked / Waiting**
- The process cannot continue execution until an **external event** occurs.
- Common reasons:
  - Waiting for I/O completion
  - Waiting for a resource
  - Waiting for user input
- While blocked, the process **does not compete for the CPU**.

Example:
- A process reading data from disk remains blocked until the I/O operation completes.

---

### 5. **Terminated**
- The process has completed execution or has been aborted.
- The OS releases all resources associated with the process.
- The PCB may remain temporarily for accounting or parent-process inspection.

---

## State Transitions

The operating system moves processes between states based on events and scheduling decisions.

- **New → Ready**
  - Process creation is complete and it is admitted to the ready queue.

- **Ready → Running**
  - The CPU scheduler selects the process for execution.

- **Running → Ready**
  - The process is **preempted** due to:
    - Time slice expiration
    - Arrival of a higher-priority process

- **Running → Blocked**
  - The process requests an I/O operation or waits for an event.

- **Blocked → Ready**
  - The awaited event occurs (e.g., I/O completion).

- **Running → Terminated**
  - The process finishes execution or exits due to an error.

---

## Notes

### CPU Scheduler

The **CPU Scheduler** is a core component of the operating system responsible for selecting which process from the **ready queue** gets access to the CPU next.

Its goals include:
- Maximizing CPU utilization
- Minimizing response time
- Improving throughput and fairness

Common scheduling algorithms include:
- **First-Come, First-Served (FCFS)**
- **Round Robin (RR)**
- **Shortest Job Next (SJN / SJF)**
- **Priority Scheduling**

---

## Summary

- The five-state model provides a **simplified and clear view** of process execution.
- Processes transition between states based on scheduling and system events.
- The model is fundamental to understanding **process scheduling**, **context switching**, and **CPU utilization**.

---

