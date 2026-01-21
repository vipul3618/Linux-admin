# Operating System (OS) – Overview

## What is an Operating System?

A computer system requires hardware components such as **CPU, RAM, Storage (Hard Disk), Keyboard, and Monitor**.  
These hardware components alone do **not** make a system usable.

An **Operating System (OS)** is the **system software** that:

- Runs on the hardware
- Manages hardware resources
- Provides an interface for users and applications

### Definition

> An Operating System is an **interface between the End User and the Hardware**.

Since users usually interact with **applications**, the OS also acts as an interface between **application software and hardware**.

### Key Roles of an Operating System

- **Control Program**  
  Controls execution of application programs

- **Resource Manager**  
  Allocates and manages:
  - CPU
  - Memory
  - Storage
  - I/O devices

- **Abstraction Provider**  
  Hides hardware complexity from users and applications

---

## Why an Operating System is Required

Without an OS:

- Programs cannot run efficiently
- Hardware cannot be shared safely
- Users cannot interact with the system easily

The OS ensures:

- Efficient resource utilization
- Fair scheduling of processes
- Secure and stable system operation

---

## Operating System as Multiple Perspectives

An OS can be viewed differently depending on perspective:

- **Hardware View** → Resource allocator
- **Software View** → Application controller
- **User View** → Interface for interaction

All perspectives are valid because an OS performs **multiple responsibilities simultaneously**.

---

## Core Components of an Operating System (High-Level)

An operating system is broadly composed of the following components:

### 1. Kernel
- Core of the operating system
- Runs in **privileged mode**
- Responsible for:
  - CPU scheduling
  - Memory management
  - Process management
  - Device and I/O management

### 2. System Programs
- Provide core OS functionality
- Include:
  - Shell
  - Command interpreters
  - System-level utilities

### 3. System Utilities
- Help monitor, maintain, and manage the system
- Examples:
  - Process monitoring
  - System diagnostics
  - Package management

### 4. User Interface
- Enables interaction with the OS
- Types:
  - **CLI** (Command Line Interface)
  - **GUI** (Graphical User Interface)

---

## User Space and Kernel Space (Essential Concept)

- **Kernel Space**
  - Where the kernel executes
  - Has full access to hardware

- **User Space**
  - Where applications and user programs run
  - Cannot directly access hardware

Applications communicate with the kernel using **system calls**.

A **system call** is a secure request from a user application to the OS kernel for services it cannot perform itself,
such as accessing files, hardware, or managing processes.

---

## Summary

- The OS is essential for making hardware usable
- It manages resources, controls programs, and provides abstraction
- The kernel is the heart of the OS
- Other components support usability, control, and maintenance

---
