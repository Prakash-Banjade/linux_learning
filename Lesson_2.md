# SSH

`Secure Shell` or sometimes `Secure Socket Shell` is a protocol for `securely sending` commands to a computer `over unsecured network`.SSH uses `cryptography` to authenticate and `encrypt connections` between devices.

# Connect your local machine to the EC2 server using SSH Client

1. You will need the `.pem` file that is used while creating the instance. 
2. Open your local terminal locate the **.pem** file.
3. Head on to the connect section of your AWS EC2 instance, then move to SSH client. 
4. Copy the example and run the example on your local machine with sudo command.
```bash
sudo ssh -i "your_key.pem" ubuntu@ip-exampleIP
```

This is how you SSH to your EC2 instance.

# Update your LINUX system

Open your local terminal and run the command below to update your system.
```bash
sudo apt-get update
```

# Install packages

You can install different packages like git, docker, python, etc.
```bash
sudo apt-get install git
```

## Update your packages
```bash
sudo apt-get update
```

As you install a package, you will see a line at bototm like 'Process trigger for man-db'. So what is `man` here? 
## Man
Man is a system for reading and displaying documentation. Man is a manual page for a specific command.

1. To read a man page, type `man` followed by the name of the page you want.
```bash
man man
```
2. Manual page for `ls`:
```bash
man ls
```

3. To display all available man pages, type `man -k`.
```bash 
man -k
```

# Server Copy (SCP) command

Using `scp` command, you can copy files from one server to another. This means you can copy files from your local machine to the server and vice versa.

`Note` - SCP command is always executed on local machine. 

## Copy file from your local machine to the server
```bash
scp -i "your_key.pem" "your_file_name.txt" ubuntu@ip-exampleIP:~/
```
A working example of this command is given below.
```bash
prakash@PredatorPrakash:~$ sudo scp -i key-pair-prakash.pem test.txt ubuntu@ec2-16-171-3-12.eu-north-1.compute.amazonaws.com:/home/ubuntu/test_file
test.txt                                                                                            100%  100   1.8MB/s   00:00                   
```

## Copy file from the server to your local machine
```bash
scp -i "your_key.pem" ubuntu@ip-exampleIP:~/"your_file_name.txt" .
```
This will copy the file 'your_file_name.txt' from the server to your local machine in the current directory.

A working example of this command is given below.
```bash
prakash@PredatorPrakash:~$ sudo scp -i key-pair-prakash.pem ubuntu@ec2-16-171-3-12.eu-north-1.compute.amazonaws.com:/home/ubuntu/test_file test.txt
test.txt                                                                                            100%  100   1.8MB/s   00:00                   
```