### **File Management in an Operating System**

---

#### **What is a File?**

A file is a **collection of data** stored on a storage device.  
From the **Operating System’s perspective**, a file consists of two parts:

- **Data**  
  The actual content stored in the file.

- **Metadata**  
  Information that describes and manages the file.

---

#### **Metadata (Information about a File)**

Metadata contains details required by the OS to manage files efficiently:

1. **File Name / Path**  
   - Identifies the file and its location in the file system.

2. **File Size**  
   - Total size of the file in bytes.

3. **Timestamps**
   - **Created** – Time when the file was created.
   - **Last Accessed** – Time when the file was last read.
   - **Last Modified** – Time when the file content was last changed.

4. **Permissions**
   - Access rights assigned at three levels:
     - **User / Owner**
     - **Group**
     - **Others**
   - Types of permissions:
     - **Read (r)** – View file content
     - **Write (w)** – Modify file content
     - **Execute (x)** – Run the file (scripts/binaries)

5. **File Type**
   - Indicates the type of file:
     - Regular file
     - Directory
     - Symbolic link
     - Device file

6. **Owner / User**
   - User who owns the file.

7. **Group**
   - Group associated with the file.

8. **Link Count**
   - Number of **hard links** pointing to the file.

9. **Data Block Information**
   - Information about disk blocks where file data is stored.

10. **Inode Number** *(Linux-specific but essential)*  
    - Unique identifier for the file in the file system.

---

#### **Purpose of File Management**

The OS performs file management to:

- Organize data efficiently
- Control access and security
- Track file locations on disk
- Support file creation, deletion, and modification
- Ensure data integrity

---

#### **Summary**

- A file is made up of **data and metadata**
- Metadata allows the OS to manage files effectively
- Permissions, ownership, and timestamps play a key role in security
- File management is a core responsibility of the OS

---
