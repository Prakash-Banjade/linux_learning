# Shell scripting

## Introduction

Shell scripting is the art of writing scripts (sets of commands) in a shell language to automate tasks or to interact with the operating system.

## Example
```bash
echo "Hello World"
```

More examples: [SHELL_SCRIPTING](SHELL_SCRIPTING.md)

## Why Shell scripting?

Shell scripting is primarily used to automate repetitive system tasks, such as backing up files, monitoring system resources, and managing user accounts. By turning a series of commands into a script, system administrators can save time, increase accuracy, and simplify complex tasks.

## Tool used
BASH (Bourne Again SHell) – It is the most widely used shell in Linux systems. It is used as default login shell in Linux systems and in macOS.

### Check which bash you are using

```bash
which bash

/usr/bin/bash
```
This means you are using /bin/bash.

## Writing shell scripts

1. Create a shell script file with extension .sh

```bash
touch script.sh
```

2. Write your script in the file

```bash
nano script.sh
```

3. Inside script.sh file, write your commands

```bash
#!/bin/bash

...(Rest of your script)
#You must have to define you bash at very first line.
```

Example script:

```bash
#!/bin/bash
echo "Hello World"
```

4. Save your script file
5. Running your script
```bash
bash script.sh
```
This will print "Hello World"

## How to check the permission of a file?

To check the permission of a file, you can use the `ls -l` command.

```bash
ls -l script.sh
```
You will see something like this:
```bash
-rw-rw-r-- 1 ubuntu ubuntu 54 May 10 17:16 script.sh
```
This means that the file is readable by the owner, writable by the owner, but not executable by the owner.

## Making a script executable

Making a script executable in Linux means `giving it permission` to be `run as a program`. In Linux, files have permissions that control who can read, write, and execute them. When a script is executable, it means that users can execute the script like any other program or command.

To make a script executable, you need to use the chmod command to change its permissions.

```bash
chmod +x script.sh
```
Or, 
```bash
chmod 777 script.sh
```

Now if you try to see the permissions of the script, you will see that it is now executable:

```bash
-rwxrwxr-x 1 ubuntu ubuntu 54 May 10 17:16 script.sh
```

After making the script executable, you can run it by simply typing its name preceded by ./ in the terminal, like this:

```bash
./script.sh
```