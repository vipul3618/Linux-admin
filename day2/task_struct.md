# task_struct in Linux

## What is task_struct?

`task_struct` is the fundamental data structure used by the Linux kernel to represent a **process**
(or more precisely, a **task** — since Linux treats processes and threads similarly).

- It acts as the **Process Control Block (PCB)** of Linux.
- Every time a new process is created (via `fork()`, `clone()`, etc.),
  the kernel allocates and initializes a new `task_struct` for it.

---

## Size

- Historically around **4 KB**
- In modern kernels, the size varies depending on configuration and enabled features

---

## Defined in

- include/linux/sched.h
---

## What Information Does task_struct Store?

It contains **all the information** the kernel needs to manage a process:

### 1. Process Identification

| Field  | Description     |
|--------|-----------------|
| `pid`  | Process ID      |
| `tgid` | Thread Group ID |
| `ppid` | Parent Process ID |

### 2. Scheduling Information

- Process state (`TASK_RUNNING`, `TASK_INTERRUPTIBLE`, etc.)
- Priority
- Scheduling policy
- CPU time statistics
- Links to scheduler run queues

### 3. Memory Management

- Pointer to `mm_struct`
- Virtual memory layout
- Heap and stack information
- Page tables

### 4. File System Information

- File descriptor table
- Current working directory
- Root directory

### 5. Signal Handling

- Pending signals
- Signal handlers

### 6. Timers

- Interval timers
- CPU timers

### 7. Credentials & Security

- User ID (UID)
- Group ID (GID)
- Capabilities

### 8. Relationships

- Parent process
- Children list
- Sibling processes

---

## Other Names for PCB

The **Process Control Block (PCB)** may also be referred to as:

| Name                        | Context                  |
|-----------------------------|--------------------------|
| **Process Descriptor**      | General OS terminology   |
| **U-area (uarea)**          | Older UNIX terminology   |
| **task_struct**             | Linux kernel             |

---

## Process Lists and Queues in Linux

When you run:

```bash
ps -e
```

- It shows all running processes because the kernel maintains internal
data structures tracking every task_struct.

# Process Lists and Queues in Linux

---

## 1️⃣ Job Queue / Process List

- Maintained as a **doubly linked list**
- Headed by `init_task`
- Contains **all processes** currently in the system
- Each `task_struct` is linked to others

---

## 2️⃣ Ready Queue (Run Queue)

- Contains processes **ready to execute**
- Managed by the **CPU scheduler**
- The scheduler selects a process from the run queue

---

## 3️⃣ Waiting Queues

There are **multiple waiting queues** in the system.

Processes enter a waiting queue when they are:

- Waiting for **I/O**
- Waiting for a **device**
- Sleeping for a **timer**
- Waiting for a **lock**

### Examples

| Wait Queue                  | Reason                         |
|-----------------------------|--------------------------------|
| Disk I/O wait queue         | Waiting for disk read/write    |
| Keyboard input wait queue   | Waiting for user input         |
| USB device wait queue       | Waiting for USB device response|

> Each device or event may have its own waiting queue.

---

## Important Clarification

> In Linux:
>
> - A **process** and a **thread** are both represented by `task_struct`
> - Threads share certain resources (like memory),
>   but each thread has its **own** `task_struct`
