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
- Type `cd` to change directory to user's home directory from any directory.  
  - You can also use `cd ~` to get to the user's home directory
  - `cd -` to move to the previous directory

### Video2: Manipulating Files
- `touch`, `mv`, `rm`
  - `rm` removes files permanently.
 - `cat` - concatinate. Used to view file contents and create file too `cat old.txt>new.txt`
 - `more` - to view contents of a file, click space for moving down the page. `q` to exit
 - `less` - to view contents of a file, and move line by line using arrows and space bar to pagedown. `q` to exit
 - You can use any editors like vim, nano to create and edit files from terminal.

### Video3: Finding Information
- `rmdir` removes empty directory
- `rm -r` removes files and folders recursively. `rm -ir` interactive delete.
- `find / -name "filename"` - Find with name from `/`(root directory). This will show some permission errors.
  - `find / -name "filename" 2>/dev/null` - 2 tells the terminal to redirect the error to /dev/null (where it is deleted) and show results.  
  This command will look for files with name `filename` in the specified directory.
  - `find / -name "*filename*" 2>/dev/null` - will show files containing `filename` text in its name.
- `grep` tells terminal to search for regular expressions
  - `find / -name "*backup*" 2>/dev/null` - This will return long list of files from many directories  
  We can use | (pipeline) to pass output of a command as input of other command.
  - `find / -name "*backup*" 2>/dev/null | grep $USER` - This will pass the output of `find` command to grep, Then grep will search for outputs with username.
  **Learn regular expressions to use grep with more features**  
- **Bash keeps history of the commands we have executed**
  - `history` - to see the list of commands executed. (Even after shutdown)
  - `!ls` (! - Bang) - To execute the last executed `ls` command.
  - `history | grep cat` - To find the history of usage of grep command
  
### Video4: Aliases
- You can set`ll` as an alias of `ls -laF` by `alias ll='ls -la'
- `alias` - To see the list of all aliased commands
- We can create a file `.bash_aliases` to create list of all aliases you need to use.  
To let terminal know our alias commands run `source .bash_aliases`
- There are other files like `.bash_history`, `.bash_logout` Checkitout
- To keep the aliases whenever you need, add the file to startup.

### Video5: Writing a Shell Script
- #!/bin/bash - This is a note to the interpreter that this is a bash script
- # - is comment in bash
- VAR=`date %d%m%Y` - will save the date to VAR variable ( **\`** is used to run the command)
- To get value of stored variables use $VAR.
- To run a file `./file`(only if file has executable permission) or `source file`
  - `chmod` to manage file permissions
    - `chmod u=rwx filename` - to give set permission for user for that particular file
    - `chmod u-x filename` - to remove the permission to execute from the user
    - `chmod u+x filename` - to add the permission to x
 - Refer the mybackup file for the script to create a backup
 
 ### Video6: Bash Scripting and Creating a Cron Job With Crontab
 - `crontab` - crontable to schedule tasks. `crontab -l` to see the tasks we have set
 - `crontab -e` to edit the crontab file to add tasks.
 - `crontab -r` to remove tasks in the current user account
 - crontab shortcuts to add tasks in `crontab -e`
  - @yearly /path/to/job or @annually /path/to/job
  - @monthly /path/to/job
  - @weekly /path/to/job
  - @daily /path/to/job or @midnight /path/to/job
  - @hourly /path/to/job
  - @reboot /path/to/job - This is useful for adding custom scripts
 
