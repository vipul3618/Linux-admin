# Process Management

A **process** is a **program under execution**, while a **program** itself is just a set of instructions stored on disk.

A program written in a `.c` file does **nothing** until it is:
1. Compiled into an executable binary  
2. Loaded into memory  
3. Executed by the CPU  

Until then, it remains **static**.

A `.c` file sitting on disk is only source code. Even after compilation, the resulting executable file (for example, `.out` or `.exec`) is still **static**. A program becomes a **process** only when the operating system loads it into memory and starts its execution.

---

## From Source Code to Process

There are several steps through which a static `.c` file passes before it becomes a running process. This sequence of tools is commonly referred to as a **toolchain**.

**Source Code** → **Preprocessor** → **Compiler** → **Assembler** → **Linker** → **Executable binary** → **OS Loads it in Memory** → **Executed**


---

## Toolchain Components

### **Preprocessor**
- Handles preprocessor directives (`#include`, `#define`, `#ifdef`, etc.)
- Removes comments
- Expands macros

### **Compiler**
- Checks for syntax and semantic errors
- Creates a **symbol table** for variables and functions
- Converts high-level code into **assembly language**

### **Assembler**
- Converts assembly code into **machine (binary) code**

### **Linker**
- Resolves external symbols and library references
- Links object files and libraries
- Produces the final **executable binary**

### **Debugger**
- Used to inspect program execution
- Helps identify logical and runtime errors

---

## From Executable to Active Process

Even after an executable file is created, it remains on disk until it is executed.

When you run:
```bash
./program.exec

```
The operating system makes a system call (such as `execve()`) to:

- Load the executable into memory
- Replace the current process image with the new program
- Allocate required system resources

At this point, a **process is created**.

---

## Structure of an Executable File

An executable file typically contains the following sections:

- **Executable Header**
- **Text Segment**
- **Data Segment**
- **BSS Segment**
- **Read-Only Data**
- **Symbol Table**

---

## Memory Allocation by the Kernel

The operating system relies on the kernel to manage:

- Memory allocation
- CPU scheduling
- I/O handling
- Process lifecycle

The kernel creates the environment required for processes to execute and manages access to system resources.

---

## Loading the Executable into Memory

When an executable is loaded, the following segments are placed into RAM:

### Text Segment
- Contains executable instructions
- Read-only
- Holds compiled machine code (functions, loops, logic)

### Data Segment
- Stores initialized global and static variables

### BSS Segment (Block Started by Symbol)
- Stores uninitialized global and static variables
- Automatically initialized to `0` by the OS

### Read-Only Data Segment
- Stores constants and string literals

### Heap
- Used for dynamic memory allocation
- Grows upward during execution
- Managed using `malloc()`, `calloc()`, and `free()`

### Stack
Stores:
- Function parameters
- Local variables
- Return addresses

Additional details:
- A stack frame is created on every function call
- Grows downward during execution

---

## Process Control Block (PCB)

Each process is represented in the OS by a **Process Control Block (PCB)**.

The PCB stores metadata required to manage and control a process, including:

- Process ID (PID)
- Process state (running, waiting, terminated, etc.)
- Program Counter (next instruction to execute)
- CPU registers
- Memory management information (text, data, heap, stack pointers)
- Open file descriptors
- I/O status
- Scheduling priority

---

## Process Inspection Commands

Linux provides several commands to inspect running processes:

### `top`
- Displays real-time process information
- Shows CPU and memory usage

### `ps`
- `ps` → current shell processes
- `ps -e` → all running processes
- `ps -e -o pid,ppid,cmd` → detailed process information

### `tty`
- Displays the terminal device associated with the current session

