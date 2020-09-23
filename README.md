# Introduction-to-Bash-Shell-Scripting

### Video1: Navigation
- Open cli(terminal) from gui or using `ctrl + t` to execute commands.
- `echo $SHELL` - returns the shell running on the terminal
  - Generally in linux you will find bin/bash which is the bash shell. Bash - Bourne Again Shell  
  There are many other shells like c-shell, z-shell, korn-shell.  
- `ls` - to list directories  
    - `ls -al` list with options. Here by `-` we are saying that we are starting with some options, `a` - stands for all (shows hidden files), `l` - long listing format.
    ```
    total 68
    drwxr-xr-x  2 rhyme rhyme  4096 May 25 05:03 .
    drwxr-xr-x 27 rhyme rhyme  4096 Sep 22 22:19 ..
    -rwxr-xr-x  1 rhyme rhyme  4693 Jul 10  2018 exo-terminal-emulator.desktop
    -rw-------  1 rhyme rhyme 50417 May 25 05:03 rhymeemail.png
     ```
     - Here the first column denotes the type and permissions for that files.
      - If starts with `d` it is directory, elseif it starts with `-` then it is a file.
      - `r` read, `w` - write, `x` - execute permissions.
     - 2nd column and 3rd column are user and group respectively.
     - 4th column shows the size in bytes and the time last accessed.
     - Last column shows the Name of the file or directory
- `man ls` to know more about ls command or any other command at anytime. To quit man page press `q`.
- `pwd` to see the current directory you are in. Generally terminal starts with the user's directory
- Type `cd` to change directory to user's home directory from any directory. You can also use `cd ~` to get to the user's home directory

### Video2: Manipulating Files
-


