## Defining variables

```bash
#!/bin/bash

name="Prakash Banjade"

echo $name # output: Prakash Banjade

echo "Hello ${name}" # output: Hello Prakash Banjade
```

**Note**: `BASH` is a reserved word in Linux. So you cannot use it as a variable name.

## Taking user input

```bash
#!/bin/bash

echo "Enter your name: "
read name

echo "Hello ${name}"
```

## Comments

```bash
#!/bin/bash

# This is a comment
```

## Making a pause (set timeout)

```bash
#!/bin/bash
echo "Hello there!"
sleep 4
echo "How are you?"
sleep 2
echo "This message is delayed using 'sleep' command"
```

## Passing arguments to a script

Inside script:
```bash
#!/bin/bash
echo "Hello $1" # $1 is the first argument passed to the script
```

Now execute the script:

```bash
./script.sh Prakash
```

You will see the output: `Hello Prakash`

## If statement

```bash
#!/bin/bash

if [ "$1" = "Prakash" ] # Must use space after and before brackets, put the argument inside quotation marks
then
 echo "Hello $1"
else
 echo "You are not Prakash"
fi // Must close if statement using fi
```

## If elseif else statement

```bash
#!/bin/bash

if [[ $1 -gt $2 && $1 -gt $3 ]] # while using -gt or && operators use double brackets
then
echo "$1 is largest"
elif [[ $2 -gt $1 && $2 -gt $3 ]]
then
echo "$2 is biggest"
else
echo "$3 is biggest"
fi
```


## For loop

```bash
#!/bin/bash

for ((i=0; i<=10; i++)) # must use double parantheses
do
echo "$i"
done
```

### Creating multiple files

```bash
#!/bin/bash

for ((i=0; i<=10; i++))
do
touch "$i.txt"
done
```
OR, (Using command line)

```bash
touch file{0..10}.txt
```

### Iterate through files

```bash
#!/bin/bash

for file in *.txt # *.txt means all txt files, you can use * for all files
do
echo $file # here you can simply remove files by using rm command
done
```

## Functions

```bash
#!/bin/bash

hello() { # function definition
  echo "Hello $1"
}

hello Prakash # calling the function with argument Prakash
```

### Function to add users

```bash
#!/bin/bash

add_user() {
user=$1
password=$2

useradd -m -p $password $user && echo "User $user has been created"
}

# calling function: creating user with username Prakash and password 123456
add_user Prakash 123456
```
Now you can check the users using command: `cat /etc/passwd`

## Date and time

```bash
#!/bin/bash

curr_timestamp=$(date "+%Y-%M-%D-%H-%M-%S") # date is an inbuilt command/function in Linux
echo $curr_timestamp # output: 2022-01-01-01-01-01
```