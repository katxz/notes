# Bash Scripting

## Debug Flag

`-x` flag after `shebang` adds debug output

```text
#!/bin/bash -x
```

## Single/Double Quotes

Bash treats single and double quotes differently. 

* When encountering single quotes, Bash interprets every enclosed character literally. 
* When enclosed in double quotes, all characters are viewed literally except `$`, `````, and `\` meaning variables will be expanded in an initial substitution pass on the enclosed text.

```text
kali@kali:~$ greeting='Hello World'
kali@kali:~$ greeting2="New $greeting"
kali@kali:~$ echo $greeting2 
New Hello World
```

## Command Substitution

Command substitution allows us to take the output of a command or program \(what would normally be printed to the screen and have it saved as the value of a variable.

```text
kali@kali:~$ user=$(whoami)
kali@kali:~$ echo $user 
kali
```

Command substitution happens in a subshell and changes to variables in the subshell will not alter variables from the master process. 

Note command substitution can also be done using backticks \(`````\). However this is the older style and usage is discouraged.

## **Special Bash Variables**

| **Variable Name**  | **Description**  |
| :--- | :--- |
| $0  | The name of the Bash script  |
| $?  | The exit status of the most recently run process  |
| $@  | All arguments passed to the Bash script  |
| $\#  | Number of arguments passed to the Bash script  |
| $$  | The process ID of the current script  |
| $1 - $9  | The first 9 arguments to the Bash script  |
| $HOSTNAME  | The hostname of the machine  |
| $LINENO  | The current line number in the script  |
| $RANDOM  | A random number  |
| $USER  | The username of the user running the script  |

## Bash Script Commands

### read

* `-p`, specify a prompt
* `-s`, make the user input silent

```bash
#!/bin/bash

read -p 'Username: ' username
read -sp 'Password: ' password

echo "Thanks, your creds are as follows: " $username " and " $password
```

### **test**

The square brackets \(`[` and `]`\) in the if statement are actually a reference to the `test` command. Some of the most common `test` operators include:

| **Operator**  | **Description: Expression True if...**  |
| :--- | :--- |
| !EXPRESSION  | The EXPRESSION is false.  |
| -n STRING  | STRING length is greater than zero  |
| -z STRING  | The length of STRING is zero \(empty\)  |
| STRING1 != STRING2  | STRING1 is not equal to STRING2  |
| STRING1 = STRING2  | STRING1 is equal to STRING2  |
| INTEGER1 -eq INTEGER2  | INTEGER1 is equal to INTEGER2  |
| INTEGER1 -ne INTEGER2  | INTEGER1 is not equal to INTEGER2  |
| INTEGER1 -gt INTEGER2  | INTEGER1 is greater than INTEGER2  |
| INTEGER1 -lt INTEGER2  | INTEGER1 is less than INTEGER2  |
| INTEGER1 -ge INTEGER2  | INTEGER1 is greater than or equal to INTEGER 2  |
| INTEGER1 -le INTEGER2  | INTEGER1 is less than or equal to INTEGER 2  |
| -d FILE  | FILE exists and is a directory  |
| -e FILE  | FILE exists  |
| -r FILE  | FILE exists and has read permission  |
| -s FILE  | FILE exists and it is not empty  |
| -w FILE  | FILE exists and has write permission  |
| -x FILE  | FILE exists and has execute permission  |

## Syntax

### **Boolean logical operators \(&& + \|\|\)**

```bash
kali@kali:~$ echo $user2
bob

kali@kali:~$ grep $user2 /etc/passwd && echo "$user2 found!"
<nothing printed>

kali@kali:~$ grep $user2 /etc/passwd && echo "$user2 found!" || echo "$user2 not found !"
bob not found!
```

### **For Loop**

```bash
for var-name in <list> 
do
  <action to perform>
done
```

```bash
kali@kali:~$ for ip in $(seq 1 10); do echo 10.11.1.$ip; done
kali@kali:~$ for i in {1..10}; do echo 10.11.1.$i;done
```

### While Loop

```bash
while [ <some test> ] 
do
  <perform an action> 
done
```

```bash
#!/bin/bash

counter=1

while [ $counter -le 10 ]
do
  echo "10.11.1.$counter"
  ((counter++))
done
```

### **If/Else**

```bash
#!/bin/bash
# if statement example

read -p "What is your age: " age

if [ $age -lt 16 ] 
then
  echo "You might need parental permission to take this course!"
elif [ $age -gt 60 ]
then
  echo "Hats off to you, respect!"
else
  echo "Welcome to the course!" 
fi
```

### Functions

```bash
#!/bin/bash

function pass_arg {
  echo "Today's random number is: $1" 
}

pass_arg $RANDOM

echo "The previous function returned a value of $?"

return_me() {
  echo "Oh hello there, I'm returning a random value!"
  return $RANDOM 
}

return_me

echo "The previous function returned a value of $?"
```

### Local / Global Variables

```bash
#!/bin/bash

name1="John"
name2="Jason"

name_change() {
  local name1="Edward"
  echo "Inside of this function, name1 is $name1 and name2 is $name2"
  name2="Lucas"
}

echo "Before the function call, name1 is $name1 and name2 is $name2"

name_change

echo "After the function call, name1 is $name1 and name2 is $name2"
```

