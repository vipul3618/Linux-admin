# Kernel – Core of the Operating System

## What is a Kernel?

The **Kernel** is the **core component of an Operating System**.

It is the first program loaded after the bootloader and remains in memory for the entire system runtime.

> The Kernel acts as a **bridge between hardware and software**.

---

## Responsibilities of the Kernel

The kernel is responsible for managing critical system resources:

- CPU
- Memory
- Devices
- Processes

It ensures that all programs execute **safely, efficiently, and fairly**.

---

## Major Functions of the Kernel

### 1. Process Management
- Creates and terminates processes
- Maintains process states
- Handles context switching
- Enables Inter-Process Communication (IPC)

### 2. CPU Scheduling
- Decides which process gets CPU time
- Implements scheduling algorithms such as:
  - First Come First Serve (FCFS)
  - Round Robin
  - Priority Scheduling

---

### 3. Memory Management
- Allocates and deallocates RAM
- Maintains process address spaces
- Implements:
  - Paging
  - Swapping
  - Virtual memory

---

### 4. Device Management
- Communicates with hardware via **device drivers**
- Provides uniform access to devices
- Manages I/O operations

---

### 5. File System Management
- Manages file creation, deletion, and access
- Maintains metadata and permissions
- Interfaces with storage devices

---

## Kernel Space vs User Space

### Kernel Space
- Privileged mode
- Full access to hardware
- Executes kernel code and drivers

### User Space
- Restricted mode
- Runs applications and user programs
- Cannot access hardware directly

---

## System Calls

Applications cannot directly access hardware.  
They request services from the kernel using **system calls**.

Examples:
- `read()`
- `write()`
- `fork()`
- `exec()`

---

## Types of Kernels

### 1. Monolithic Kernel
- All services run in kernel space
- Faster but less modular
- Example: **Linux**

### 2. Microkernel
- Minimal kernel functionality
- Other services run in user space
- More secure but slower

### 3. Hybrid Kernel
- Combination of monolithic and microkernel
- Example: **Windows**

---

## Summary

- The kernel is the heart of the OS
- Manages CPU, memory, processes, and devices
- Runs in privileged mode
- Communicates with applications via system calls

---

