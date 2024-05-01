## Informational Commands

1. `id` - This is used to find out user and group names and numeric ID’s (UID or group ID) of the current user or any other user in the server.  
   Example:

```bash
ubuntu@ip-exampleIP:~$ id -u root
0
```

2. `whoami` - Displays the username of the current user.

3. `pwd` - Shows the present working directory (the directory you are currently in).

4. `ls` - Lists the files and directories in the current directory.

5. `uname` - Prints system information like the kernel name, node name, kernel release, etc.
   Example:

```bash
ubuntu@ip-exampleIP:~$ uname
Linux
```

6. `hostname` - Displays the hostname of the system.
   Example:

```bash
ubuntu@ip-exampleIP:~$ hostname
ip-exampleIP
```

7. `df` - Reports file system disk space usage.

8. `cat /etc/os-release` - Shows information about the operating system.

9. `uptime` - Displays how long the system has been running.

10. `w` - Shows who is logged on and what they are doing.

11. `last` - Displays a list of last logged in users.

12. `top` or `htop` - Provides a dynamic real-time view of a running system, including CPU, memory, and process usage. Like `Task Manager` in Windows.

## Operational Commands

13. `mkdir` - Create a new directory.
    Example:

```bash
ubuntu@ip-exampleIP:~$ mkdir new_folder
ip-exampleIP
```

14. `cd` - Change director. Navigate to different directory.
    Example:

```bash
ubuntu@ip-exampleIP:~$ cd new_folder
ubuntu@ip-exampleIP:~/new_folder$ cd ..
ubuntu@ip-exampleIP:~$
```

15. `touch` - Create new empty file.

```bash
ubuntu@ip-exampleIP:~$ touch test.txt
```

16. `cat` - View the content of a file.

```bash
ubuntu@ip-exampleIP:~$ cat test.txt
```

17. `nano` - Text Editor: Open a text file for editing.

```bash
ubuntu@ip-exampleIP:~$ nano test.txt

`Ctrl + X` -> Y -> Enter (Save the file)
```

18. 
