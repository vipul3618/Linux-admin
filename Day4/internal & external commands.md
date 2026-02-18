# Internal & External Commands

Basically there are two types of commands:
- Internal Commands
- External Commands

| Internal Cmds   | External Commands |
|-----------------|-------------------|
|These cmds are implemented in the shell program itself| Theses commands are implenmented seperately|
|These cmds don't have any executable on harddisk  | These cmds are available on harddisk such as /bin, /sbin, /usr/sbin|

You can use `type` command to check whether command is internal or external, it tells what kind of command is it, whether it is stored on some **path** or it would tell you that it is **builtin** with the shell.

```
❯ type cd
cd is a shell builtin
❯ type mkdir
mkdir is /bin/mkdir
❯ type ls
ls is an alias for ls -G
```

Then there is **`which`** cmd that tells what path the cmd has. You can also use `whereis` to know the mannual page and the cmd location of the where is.

```
❯ whereis alias
alias: /usr/bin/alias /usr/share/man/man1/builtin.1
```

These commands are builtin within the shell only, there is no executable logics are written within the shell only, therefore you won't see their directory. **Shell** itself is a never ending process, and thus it only ends once you end the kernal or cmd prompt process, otherwise one after another cmd shell returns back to you.

#### `open` is just like double-click

When you open a file, it opens the file using the magic number of the file through which it is able to recognise the 

#### `objdumb` and `readelf` for reading executable files

Baiscally you can read the executable files of the processes and functions used and other memory management information.

Feel free to visit information page.

#### `man bash` 

You can use `man bash` to seach for builtin commands.

#### Synchroneous Execution of Commands

The shell program waits until the program that you've entered or that you are running, say if there is a cmd like `ls` only when ls is done, the shell will return. It is same as `cat` that synchroneously execute after reading from stdout and write onto the stdout.

#### Asynchroneous Execution 

When you are executing cmd like `cat`, cat is synchroneous, but when you use the `&` after cat, you are telling the shell to not wait for the **`cat`** cmd. 

```
❯ cat &
[1] 14979
[1]  + 14979 suspended (tty input)  cat
```

Shell hasn't teminated the `cat` cmd yet.

```
14979 ttys001    0:00.00 cat
```

When you do *Contrl + C*, the process gets terminated and the shell returns backk to you. It is possible through the **SIGINT** which is an number 2 signal that stops the signal. Then, there is **SIGCONT**, another signal that is used to continue the process. *Similarly, there are many*, such that when you use `kill -l` that shows other various signals.

Remember `kill` and `pkill` are used to send the signals, they never stops or teminate the processes. 

```
❯ kill -2 14979
[1]  + 14979 interrupt  cat 
```
You can also use the cmd like `kill -SIGKILL` *process-id* to send the signals of the respective type.
```
```

Another is `pkill` that us used to send the signal to the processes using the porcess name. 
```
❯ pkill -9 cat
```
In case you need to kill the process we need `pkill` and `kill` both have there own way of using the commands as there can be different requirement for both of them.

Another cmd is using the `;` and `&&` most of the time you won't see the difference between the two but incase the first command will fail the execution of the second cmd will not occur.
```
command1 ; command2
command1 && command2
```
Then there is `&&`, `command2` will not be executed if there is failure of the `command1` but in case of the `;` this won't affect the execution of both.
