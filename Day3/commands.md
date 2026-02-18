# `chmod`

`chmod` is used to change the permission of the files and folders. Remember the **chmod** can be used in following ways:

- to remove all the permissions of the file
    ```
    ❯ ls -la testing.txt
    -rw-r--r--  1 ubuntu  staff  275 Sep 30 05:42 testing.txt
    ❯ chmod 0 testing.txt
    ❯ ls -la testing.txt
    -r--------  1 ubuntu  staff  275 Sep 30 05:42 testing.txt
    ```

- Use **`+`*permission* (r/w/x)** or `-` to add or remove the read, write, and execute permissions of the file. This can be done using the following:

```
❯ ls -la testing.txt
-r-xr-xr-x  1 ubuntu staff  275 Sep 30 05:42 testing.txt
❯ chmod -x testing.txt
❯ ls -la testing.txt
-r--r--r--  1 ubuntu  staff  275 Sep 30 05:42 testing.txt
```

- You can use `u+`*permission* in order to assign the respective level permission. For example, `g+rw`, `u+rw`, `g-rw` etc.
- You can also specify the **octal** method by providing the permission using the octal numbers. For example, `chmod 777 filename.txt`, `chmod 644 filename.txt` etc.
- Remember that you won't be able to navigate the directory if it doesn't have any executable permisssion, so you need the file executable permission to even navigate the directory.

# `chown` 

- You can use `chown` cmd in order to change the permission of ownership of the file. You need to remember that it is only through the **super user priveledge** to change the ownership of file.
    ```
    ❯ chown root next_testing.txt
    chown: next_testing.txt: Operation not permitted
    ❯ sudo chown root next_testing.txt
    ❯ ls -la next_testing.txt
    -r--------  1 root  staff  72 Sep 30 05:45 next_testing.txt
    ```

- Remember if you changed the ownership of the directory, it doesn't mean that it changes the permission of the content inside the directory, so in that case you might need `-R` which will change the permission within the directory **recursively**.

# `find`

- `find` allows you to search for particular pattern or **name** within the path or directory, using the syntax as given:
    ```
    find <path> -name <pattern>
    ```

- If you can specify the `.` and it will search for the pattern within the current working directory and its subdirectories. 
    ```
    ❯ find . -name "*.txt"
    ./testing.txt
    ❯ find . -name "*.md"
    ./linux-commands/life-cmds.md
    ./day3/day3.md
    ```
- Thus in the above example, we are using **wildcard** mask that is searching for all the .txt or .md files files within the path specified. Here in the below section we've used **~** that means search for pattern in the home directory.
    ```
    ❯ find ~ -name "*.md"
    /Users/.oh-my-zsh/CONTRIBUTING.md
    /Users/.oh-my-zsh/.github/PULL_REQUEST_TEMPLATE.md
    ....
    ```
- You can simplify your seach based on the **size** using the `-size` option in the `find`. The search will be based on the size of the file within the path specified or the current working directory.

    ```
    ❯ find . -size +200k
