# Linux Directory Structure

## Important Linux Directories

- **/boot**  
  Contains boot-related information of the operating system.  
  It stores kernel images, bootloader files, and kernel configuration files required to boot the system.

- **/bin**  
  Stands for *binary*.  
  Contains essential executable commands available to all users.  
  Example: when you run the `ls` command, its executable is located in the `/bin` directory.

- **/sbin**  
  Contains system administration commands meant to be executed only by the administrator (root user).  
  The name stands for *system binary* or *superuser binary*.

- **/etc**  
  Stores all system-wide configuration files.  
  Examples include user configuration files, network configuration, hostname information, and password-related files.

- **/root**  
  Home directory of the root (super) user.  
  Files downloaded or created by the root user are stored here.

- **/home**  
  Contains home directories for all regular users.  
  Each user has a separate directory to store personal files and data.  
  Users cannot access or modify other users’ home directories without permission.

- **/media**  
  Used for mounting removable media such as USB drives, external hard disks, CDs, and DVDs.  
  Data from these devices is accessed through this directory.

- **/mnt**  
  Used as a temporary mount point for filesystems.  
  System administrators commonly mount filesystems manually here.

- **/tmp**  
  Temporary directory used to store short-lived files.  
  Files in this directory are usually deleted when the system reboots.  
  Only store data that is required temporarily.

- **/var**  
  Contains variable data files that change frequently.  
  Commonly used for logs, spool files, and cache data.  
  Example: system and kernel logs used for troubleshooting are stored here.

- **/usr**  
  Stores user application data and non-essential system binaries.  
  It is different from `/home`, as it contains installed applications and shared resources.
  
  Common subdirectories:
  - **/usr/bin**
  - **/usr/sbin**
  - **/usr/lib**
  - **/usr/share**

- **/lib**  
  Contains shared libraries required by binaries in `/bin` and `/sbin`.  
  These libraries are essential for system boot and command execution.

- **/opt**  
  Stores optional or third-party software that is not provided by the operating system.  
  Each application usually has its own subdirectory here.

- **/dev**  
  Contains device files representing hardware devices.  
  Unlike `/media`, it stores device files, not mounted data.

- **/proc**  
  A virtual filesystem that stores information about running processes and system memory.  
  Provides real-time system information.

- **/sys**  
  Contains information about kernel modules and hardware devices.  
  Used by the kernel to expose system and device details.

---

## Virtual File System

The following directories are **virtual** and are not physically stored on the hard disk:

- **/dev**
- **/proc**
- **/sys**

These directories are created at runtime and are part of the **Virtual File System (VFS)**.

---

# Accessing Directories

### **Path**:
To access a file, you must specify its **path**.  
A path is a string that defines the location of a file or directory in the filesystem.

Example:
/proc/533
This means:
**root ( / ) → proc → 533**

---

#### **Types of Paths**

1. **Absolute Path**:
    
    - Always starts from the root (`/`).
    - Example: `/home/devops/python/demos/demo01.py`.
2. **Relative Path**:
    
    - Starts from the **current working directory**.
    - Example: If you’re already in `/home/devops`, the relative path would be `python/demos/demo01.py`.
