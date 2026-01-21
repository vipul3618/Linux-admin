### **File System in an Operating System**

---

#### **What is a File System?**

A **File System** is the method used by an Operating System to **store, organize, manage, and retrieve files** from a storage device.

It defines:
- How files are named
- How files are stored on disk
- How metadata is maintained
- How data is accessed efficiently

---

#### **File Storage Structure**

When a file is created:

- The **file data** is stored in **data blocks**
- The **metadata** is stored in a structure called **FCB (File Control Block)**
- Data blocks and metadata blocks are stored separately

> By default, a data block size is **4 KB**, which can be changed during disk formatting.

---

#### **Data Blocks**

- Smallest unit of disk storage
- Stores actual file content
- Large files use multiple data blocks

---

#### **File Control Block (FCB)**

FCB stores metadata of a file, including:

- File size
- Permissions
- Ownership
- Timestamps
- Data block pointers

---

#### **Master File Table**

The **Master File Table** maintains information about:

- Files stored in the partition
- Allocated and free data blocks
- Overall disk structure

---

#### **Volume Control Block**

The **Volume Control Block** contains:

- Volume label
- File system type
- Partition size
- Information about free space

---

#### **Boot Sector**

- Contains the **bootstrap program**
- Loads the **bootloader**
- Initiates the operating system startup

---

#### **File System Organization**

A disk is organized as:

1. Boot Sector  
2. Volume Control Block  
3. File Control Blocks  
4. Data Blocks  

This complete organization is known as the **File System**.

---

#### **Linux File System Terminology**

| General Term | Linux Term |
|-------------|------------|
| File Control Block (FCB) | iNode |
| Master File Table | iNode Table |
| Volume Control Block | Super Block |
| Boot Sector | Boot Block |

---

### **What is a File System?**

A **file system** is essentially a way of **organising files on partitions**. It provides the structure for storing and retrieving files on the disk.

#### **Types of File Systems**

Depending on the operating system or device, different file systems are used:

- **NTFS (New Technology File System)**: Used by Windows.
- **ext (Extended File System)**: Commonly used by Linux.
- **HFS (Hierarchical File System)**: Used by mac OS.
- **FAT32 (File Allocation Table 32)**: Often used in pen drives and external storage devices.


---

#### **Summary**

- File system defines how data is stored and accessed
- Data and metadata are stored separately
- Linux uses inode-based file systems
- Boot sector is essential for system startup

---
