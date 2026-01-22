# Shell

Mostly the `bash` shell is used by default, called **Born Again shell**. You can open the shell using the GUI application called Terminal that uses CLI on in the backend.

- Use `echo $SHELL` to see the default shell your are using. Because the shell being used is `zsh` and it is stored in **bin**, which means it can be used by any user.
    ```
    bash-5.2$ echo $SHELL
    /bin/zsh
    ```

There are two kinds one is GUI and CLI, that user-interface is called **Shell** and the commands are given using CLI, command prompt to interact with operating system.

1. **CLI** <br>
Windows - cmd.exe, powershell.exe <br>
Linux - bsh, bash, esh, ksh, zsh

2. **GUI** <br>
Windows - explorer.exe <br>
Linux - GNOME (GNU Network Object Modal Env), KDE (Kimman Desktop Env)


- Use `ls` *path* to see the directory within the path specified.
    ```
    bash-5.2$ ls /
    Applications	Users		cores		home		sbin		var
    Library		Volumes		dev		opt		tmp
    System		bin		etc		private		usr
    ```
You can also check the the proc directory, see there is **cpuinfo** and **meminfo**, now you can see that there are memory 

- You can check and change the date. Use `date` cmd along with options to change it.

    ```
    ❯ date
    Thu Sep 26 12:20:45 IST 2024
    ```
Go an explore different types of the options and **FORMAT** you can use in the commands.

- You can see the calender using `cal` cmd.

    ```
    ❯ cal
    September 2024     
    Su Mo Tu We Th Fr Sa  
    1  2  3  4  5  6  7  
    8  9 10 11 12 13 14  
    15 16 17 18 19 20 21  
    22 23 24 25 26 27 28  
    29 30                 
    ```

- Use `pwd` to see the current working direcotry. 

- Create multiple directories using `mkdir` *file1* *file2* *file3*.

- Use `-p` as option for creating the directories in the hierarchy within the directories.
    ```
    ❯ mkdir -p create/dir/within/the/dir
    ❯ ls
    create
    ❯ ls create/
    dir
    ❯ ls create/dir/
    within
    ❯ ls create/dir/within/
    the
    ```

- Use *Ctrl + L* in Windows and *Cmd + L* in the Mac for `clear`.

- Use `-R` for seeing the content within the directory recursivley.
    ```
    ❯ ls -R
    create

    ./create:
    dir

    ./create/dir:
    within

    ./create/dir/within:
    the

    ./create/dir/within/the:
    dir

    ./create/dir/within/the/dir:
    ```

- Create an empty file using the `touch` command.

- Use `cat` commands to **show** the contents of the file and **create** a file with content. 
    ```
    cat > file.txt 
    ❯ cat file.txt
    Testing DITISS-LINUX
    Sunbeam Information
    ```
    Remember if you tried using the command on the pre-existing file, then in that case the file content will be overidden. If you need to append the content, you can use `cat >> file.txt` meaning that you can append the data.

- Simply use `rm` to remove the file from the machine.

- Use `cp` *src*  to create a copy of the file as well to copy the file to the *path destination*, if you want to copy the direcotry to the directory, use the 

- Remember that using `mv` command you don't need `-R`

- Use `rmdir` along with the `-r` followed by the file name, if the directory is not empty.


The below are the convention that are followed in the Linux.

| | |
|-----------|-------------------|
|Hard Disk  | sda, sdb, sdc, ...|
|Partitions  | sda1, sda2, sda3, ...|


