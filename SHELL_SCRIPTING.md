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

