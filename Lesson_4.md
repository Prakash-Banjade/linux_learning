## Memory Management Commands

1. `free` - This command displays the total amount of free space available.

```bash
free
```

2. `top` - This command displays the process table.

```bash
top
```

3. `ps` - This command displays the process table.

```bash
ps
```

4. `df` - This command displays the file system table.

```bash
df
```

5. `du` - This command displays the disk usage table.

```bash
du
```

## `awk` command

Awk is a scripting language used for manipulating data and generating reports. The awk command programming language requires no compiling and allows the user to use variables, numeric functions, string functions, and logical operators

### Awk operations

1. Scans a file line by line
2. Splits each input line into fields
3. Compares input line/fields to pattern
4. Performs action(s) on matched lines

### Syntax

```bash
awk options 'selection _criteria {action }' input-file > output-file
```

### Examples

#### Filtering columns from `df` command

Suppose you want to display only the `Filesystem` column from the output of the `df` command.

```bash
df | awk '{print $1}'
```

Filtering multiple columns from `df` command

```bash
df -H | awk '{print $1, $2}'
```

Filtering rows from `df` command

```bash
df -H | awk '{print $1, $2}' | grep -v Filesystem
```

#### A shell script to check if any file system exceeded the 80% usage

1. First you need to iterate over the output of the `df` command
   
```bash
df -H | awk '{print $1, $5}' | while read line
do
  echo $line # this will show the output of the `df` command with file system name and usage 
done
```

2. Next you need to check if the usage is above 80%
```bash
alert_usage=80

df -H | tail -n +2 | awk '{print $1, $5}' | while read line
do
  usage=`echo $line | awk '{print $2}' | cut -d'%' -f1`
  filesystem=`echo $line | awk '{print $1}'`
  if [ $usage -gt $alert_usage ] # you can use -ge for greater than or equal
  then
    echo "The usage of $filesystem is $usage% which is above 80%"
  fi
done
```

Explanation:

Line 1: This will show the output of the `df` command with file system name and usage, first and fifth columns are filtered using `awk` and the output is passed to the `while` loop.
This means we have two columns, first one is file system name and second one is usage.  

The `df` command actually returns the heading also. While comapring inside the `while` loop, we are not interested in the heading. Also it will throw error for comparing string with number. So, we remove the heading using `tail` command.  

**`tail` command break down:**  

`tail`: This is the command used to display the last part of files in Linux. In this context, it's being used to display the output of the df command.  
`-n +2`: This option specifies the number of lines to output. Here, +2 tells tail to start outputting from the second line of the input. The + sign before the number indicates to start from that line number onwards. So -n +2 means "start from the second line and output all subsequent lines."

**How usage is calculated?**  

Inside while loop, we are using calculating usage of each file system. Here `line` variable is a file system name and usage.  
We are using `echo` command to get the file system which is then passed to `awk` which then filters the second column which is the usage of file system. It is then passed to `cut` command which removes the percentage sign.  
Finally, `usage` variable is assigned to the output of `cut` command.

Similarly, file system name is assigned to `filesystem` variable.

Then on line 5, we check if the usage is above 80% and if so, we print the output.