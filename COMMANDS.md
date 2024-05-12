## Informational Commands

1. `id` - This is used to find out user and group names and numeric ID’s (UID or group ID) of the current user or any other user in the server.

```bash
ubuntu@ip-exampleIP:~$ id -u root
0
```

2. `whoami` - Displays the username of the current user.

3. `pwd` - Shows the present working directory (the directory you are currently in).

4. `ls` - Lists the files and directories in the current directory.

5. `uname` - Prints system information like the kernel name, node name, kernel release, etc.

```bash
ubuntu@ip-exampleIP:~$ uname
Linux
```

6. `hostname` - Displays the hostname of the system.

```bash
ubuntu@ip-exampleIP:~$ hostname
ip-exampleIP
```

7. `df` - Reports file system disk space usage.
```bash
ubuntu@ip-exampleIP:~$ df -H
```

8. `cat /etc/os-release` - Shows information about the operating system.

9. `uptime` - Displays how long the system has been running.

10. `w` - Shows who is logged on and what they are doing.

11. `last` - Displays a list of last logged in users.

12. `top` or `htop` - Provides a dynamic real-time view of a running system, including CPU, memory, and process usage. Like `Task Manager` in Windows.

13. `ifconfig` - Network Configuration: Display or configure network interfaces.

14. `ip` - IP Configuration: Manage IP addresses and network settings.

```bash
ubuntu@ip-exampleIP:~$ ip addr show
```

15. `netstat` - Network Statistics: Display network connections and statistics

```bash
ubuntu@ip-exampleIP:~$ netstat -tuln
```

16. `free` - This command displays the total amount of free space available.

```bash
ubuntu@ip-exampleIP:~$ free -m
```

17. `curl` - Check Website Connectivity: Check if a website is up.

```bash
ubuntu@ip-exampleIP:~$ curl -Is https://example.com | head -n 1
```

18. `dig` - Domain Information Groper: Retrieve DNS information for a domain.

```bash
ubuntu@ip-exampleIP:~$ dig example.com
```

19. `lsof` - List Open Files: List open files and processes using them.

```bash
ubuntu@ip-exampleIP:~$ lsof -i :port
```

20. `history` - Show command history.

```bash
ubuntu@ip-exampleIP:~$ history
```

21 `which` - Show the location of a command.

```bash
ubuntu@ip-exampleIP:~$ which command{bash, ls, nano}
```

## Operational Commands

13. `ps` - Process Status: Display running processes.

```bash
ubuntu@ip-exampleIP:~$ ps aux
```

13. `mkdir` - Create a new directory.

```bash
ubuntu@ip-exampleIP:~$ mkdir new_folder
ip-exampleIP
```

14. `cd` - Change director. Navigate to different directory.

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

18. `mv` - Move: Move files or directories.

Syntax: `mv source destination`

```bash
ubuntu@ip-exampleIP:~$ mv test.txt new_folder
```

`test.txt` file will be moved inside folder `new_folder`

19. `cp` - Copy: Copy files or director. Same as `mv` but copy the item.

20. `rm` - Remove: Delete files or directories.

```bash
ubuntu@ip-exampleIP:~/new_folder$ rm test.txt
```

21. `grep` - Search Text: Search for text patterns in files.

Syntax: `grep "pattern" file.txt`

```bash
ubuntu@ip-exampleIP:~$ grep "Hey" newFile.txt
```

22. `find` - Search Files and Directories: Search for files and directories.

Syntax: `find /path/to/search -name "file_name"`

```bash
ubuntu@ip-exampleIP:~$ find . newFile.txt
```

24. `kill` - Terminate Processes: Terminate a process using its ID.

25. `wget` - Download Files: Download files from the internet.

```bash
ubuntu@ip-exampleIP:~$ wget https://example.com/file.zip
```

26. `curl` - Transfer Data with URLs: Transfer data to or from a server

```bash
ubuntu@ip-exampleIP:~$ curl -O https://example.com/file.txt
```

27. `tar` - Archive and Extract: Create or extract compressed archive files.

```bash
ubuntu@ip-exampleIP:~$ tar -czvf archive.tar.gz folder
```

28. ssh - Secure Shell: Connect to a remote server securely.

```bash
ubuntu@ip-exampleIP:~$ ssh user@remote_host
```

29. `scp` - Securely Copy Files: Copy files between local and remote systems using SSH.

```bash
ubuntu@ip-exampleIP:~$ scp file.txt user@remote_host:/path
```

30. `at` - Execute Commands Later: Run commands at a specified time.

```bash
ubuntu@ip-exampleIP:~$ echo "command" | at 15:30
```

31. `ping` - Network Connectivity: Check network connectivity to a host.

```bash
ubuntu@ip-exampleIP:~$ ping google.com
```

32. `useradd` - Add User: Create a new user account.

```bash
ubuntu@ip-exampleIP:~$ useradd -m -p password username
```

13. `usermod` - Modify User: Modify user account properties.

```bash
ubuntu@ip-exampleIP:~$ usermod -aG groupname username
```

14. `passwd` - Change Password: Change user password.

```bash
ubuntu@ip-exampleIP:~$ passwd username
```

15. `sudo` - Superuser Do: Execute commands as the superuser.

```bash
ubuntu@ip-exampleIP:~$ sudo command
```
