![20221108_112906](https://user-images.githubusercontent.com/71178740/200482714-87f3fc9e-fead-45d0-99a5-e6d829cdd45d.jpg)


<p id="top"></>

## Introductions

* [All About Of Shell/Bash/Shell Scripting/Bash Scripting](https://www.datacamp.com/blog/what-is-shell)

<details>
<summary>BASIC INTRO</summary>

### 🤔 What is Shell & Shell Scripting?
> A shell is a type of computer program called a command-line interpreter that lets Linux and Unix users control their operating systems with command-line interfaces. Shells allow users to communicate efficiently and directly with their operating systems. 

> Shell scripting is a method to automate tasks as a collection of commands. The bash script is one form of shell script. Shells may be one of Korn, C shell, Bourne, Bash, etc

### 🤔 What is Bash?
> Bash scripting is a subset of shell scripting. In basic terms, Bash is a command line interpreter that typically runs in a text window where user can interpret commands to carry out various actions. The combination of these commands as a series within a file is known as a Shell Script. Bash can read and execute the commands from a Shell Script.

### 🤔 What is Script?
> In computer programming, a script is a program or sequence of instructions that is interpreted or carried out by another program rather than by the computer processor (as a compiled program is).

> A script is sometimes used to mean a list of operating system commands that are prestored in a file and performed sequentially by the operating system's command interpreter whenever the list name is entered as a single command.

</details>


### Usages Of Bash

*It is used by the System Administrators, Network Engineers, Developers, Scientists, and everyone who use Linux/Unix operating system. They use Bash for system administration, data crunching, web application deployment, automated backups, creating custom scripts for various pages, etc.*

* ## [Bash Commands](core/bashcommand.md)

<p id="Top"></>

### Topics To Learn In Bash Scripting
* [Variables](#Variables)
* [Operators](#Operators)
* [User input](#User)
* [Dates](#Dates)
* `Conditional Statements`
   * [If,else,else if](#Conditional)
   * [Case](#Conditional)
* `Loops`
   * [For](#Loops)
   * [While](#Loops)
   * [Untill](#Loops)
* [Function](#Function)
* [Arrays](#Arrays)
* [Strings](#Strings)
* `Miscellaneous`
   * [Comments](#Comments)
   * [Sleep](#Sleep)
   * [Read File](#Read)
   * [Write File](#Write)
   * [File/Folder Exists or Not](#File)

---
<p id="Variables"></>

## Variables:
```sh
a=10
b=20
c='hello'
d=a+b
```

<a href="#Top">↑ Back To Top</a>

<p id="Operators"></>

## Operators:
```sh
+,-,*,/,%,[** --> # Power]
+=,-=,*=,/=,%=

#!/bin/bash  

# Performing Arithmetic Operations in Bash:
name="Fazle Rabbi"
age=20
echo $name
echo "$name"
# With Dolar Sign (1):
sum=$((a+b))
echo $sum

a=30
b=40
# Without Dolar Sign (2):
((sum=a+b))
echo $sum

# Changing Value:
((a+=10))
echo $a

# Changing Value Using Let (3):
let "a=$((a+100))"
echo $a

# Using Backticks (4):
x=99
y=1
sum=`expr $x + $y`
echo $sum

```

<p id="Uinput"></>

<a href="#Top">↑ Back To Top</a>

<p id="User"></>

## User Input:
```sh
#!/bin/bash

echo -n "Type Your Name:"
read name
echo "Hi, $name"

# -p --> Prompt
read -p "Enter Your DOB:" age
echo "You are, $((2022-age)) years old!"

# Multiple User Input:
read id gpa roll
echo "id: ${id}, gpa: ${gpa}, roll:${roll}"

# When don't pass any variable with the read command?
read
echo $REPLY

# Secure Input:
read -sp "Type Your Password:" pass
echo "Your Password is: ${pass}"

# Multiple inputs using an array:
read -a names
echo -e "${names[1], ${names[1]}}"
echo "${names[0]}"

```

<p id="Dates"></>

<a href="#Top">↑ Back To Top</a>

<p id="Dates"></>

## Dates:
* [Details Info](https://www.javatpoint.com/bash-date-format)
```sh
#!/bin/bash

d=`date +%m-%d-%Y`  
echo $d
```

<p id="Conditional"></>

<a href="#Top">↑ Back To Top</a>

<p id="Conditional"></>

## Conditional Statement:

* ***If,else if,else:***
```sh
#!/bin/bash

clear

# Syntax:
x=10
# x=109
if [ $x == 10 ]; then
echo "Hey!"
else if [ $x == 109 ]; then
   echo "Hi!"
else
echo "Hello!"
fi
fi

# Use Multiple Condition:
if [ $x == 10 ] && [ $x > 11 ]; then
   echo "Okey!"
fi

# Another Way:
if [[ $x == 10 && $x <20 ]]; then
   echo "Okey!"
fi

# gt,lt,eq --> >,<,=
if [ 8 -gt 7 ] || [ 10 -lt 3 ];  
then   
echo " Condition is true. "  
fi

# Options for If statement in Bash Scripting:
# --------------------
# -n --> Check for, STRING is greater than zero!
# -z --> Check for, STRING length is equal to zero!
# !,==,!=,[-eq,-gt,-lt] --> INTEGER!
# -d --> To check if FILE exists and it is a directory.
# -e --> To check if FILE exists.

# --------------------
x=10
if [ ! $x ]; then
   echo "True"
else
   echo "False"
fi

# elif:
a=10
if [ $a == 20 ]; then
   echo "hi"
elif [ $a == 10 ]; then
   echo "Im Working!"
else
   echo "Oops! Condition False!"
fi

```
* ***Case***:
```sh
#!/bin/bash

read -p "Enter Your Mark:" mark
case $mark in
   80)
      echo "You Got A+"
      ;;
   70|71)
      echo
      echo "You Got A-"
      ;;
   *)
      echo "Default Value!"
esac

```

<p id="Loops"></>

<a href="#Top">↑ Back To Top</a>

<p id="Loops"></>

## Loops:
```sh
#!/bin/bash

clear

# ----------------------
#     For Loop         #
# ----------------------
# (Syntax 1):
for (( i = 0; i < 10; i++ )); do
   echo "i love bash!"
done

# (Syntax 2):
str="I Love Coding"
for value in $str
do
   echo "The value is: $value"
done

# Read a range:
for num in {1..10..2};
do
   echo "The number is: $num"
done

# Read Array Variables:
names=("Smith" "David" "John")
for name in "${names[@]}"
do
   echo "Name: $name"
done

# Break & Continue:
# --> Same as other language!


# ------------------------
#     While Loop         #
# ------------------------
x=10
while [ $x -lt 20 ] 
do
((x++))
echo "Hey, $x"
done

# Like c Syntax:
i=0
while((i < 10))
do
echo "C Like Syntax"
((i++))
done


# ------------------------
#     Until Loop         #
# ------------------------
# Example 1:
i=1  
until [ $i -gt 10 ]  
do  
echo $i  
((i++))  
done  

# Example 1:
x=0
read -p "Enter a number:" num
until [ $x -gt $num ];
do
   echo "Send email --> $x"
   ((x++))
done

```

<p id="Functions"></>

<a href="#Top">↑ Back To Top</a>

<p id="Function"></>

## Function
```sh
#!/bin/bash  

# Function Declaration
function sum(){
   result=$(($1+$2))
   echo "$result"
   return 5
}

# Call The Function
sum 10 20 30

# Return Value Receive
rem="$(sum 10 99)"
echo "$rem"
echo $?

```

<p id="Arrays"></>

<a href="#Top">↑ Back To Top</a>

<p id="Arrays"></>

## Arrays:
<details>
<summary>View Code</summary>

```sh
#!/bin/bash  

#-------------------------
# Method 1 Of Creating Array:
#------------------------- 
declare -A demo 
demo[0]='Hello There Im the owner of this script!'
demo[1]='Hey,Fazle Rabbi!'

echo "${demo[0]}"
echo "${demo[1]}"

# The above form in the following way::
# Declaration:
declare -A demo2  

# Bash Array Initialization:
demo2=(  
    [a]=username  
    [1]=email  
    [2]=phone  
)  

# Access Elements of Bash Array:
echo "${demo2[a]}"
echo "${demo2[1]}"
echo "${demo2[2]}"

# Print Bash Array:
declare -p demo2  

echo #For New Line


#------------------------- 
# Another way to create an array:
#------------------------- 
ARRAY_NAME=('Apple' 'Orange' 'Banana')  
echo "${ARRAY_NAME[0]}"
echo "${ARRAY_NAME[1]}"
echo "${ARRAY_NAME[2]}"
echo #For New Line
echo "${ARRAY_NAME[@]}" #Print All Element
echo
sleep 1s
# Iterate array element using loop:
for x in "${ARRAY_NAME[@]}" ; do
   echo "The value is: $x"
done

# Print the [key/number] of array:
echo "${!ARRAY_NAME[@]}"

# Finding Array Length:
echo "${#ARRAY_NAME[@]}"

echo


#------------------------- 
#Script to loop through an array in C-style  
#------------------------- 
declare -a example_array=( "Welcome" "To" "Javatpoint" )  
#Length of the Array  
length=${#example_array[@]}  
#Array Loop  
for (( i=0; i < $length; i++ ))  
do   
echo $i ${example_array[$i]}  
done  

echo

# Adding Elements to an Array
declare -a example_array=( "Java" "Python" "PHP" "HTML" )  
#Adding new element  
example_array[4]="JavaScript"  
#Printing all the elements  
echo "${example_array[@]}"

echo

# Another method for adding a new element to an array:
example_array+=( JavaScript CSS SQL )  

echo

SLICED_ARRAY=(${example_array[@]:0:3})
# ^--> Java,Python

for i in "${!SLICED_ARRAY[@]}"
do
echo "${i} : ${SLICED_ARRAY[i]}"
done
```

</details>

<p id="Strings"></>

<a href="#Top">↑ Back To Top</a>

<p id="Strings"></>

## Strings

```sh
a='Hello'
b='Javatpoint'

result=$a = $b  #   
result=$a != $b #
result=$a \< $b # Less then or equal
result=$a \> $b # Greater then or equal
result= -n $str # Zero or greter then Zero
result= -z $str # Zero or Not Zero --> like [true,false]

```

* ***Length Of Strings:***
```sh
str="Hello"  
a=${#str}
b=`expr length "$str"`
echo "$a"
echo "$b"
```

* ***Split A Strings:***
```sh
str="Hello"  
a=${#str}
b=`expr length "$str"`
echo "$a"
echo "$b"
```

<p id="top"></>

<a href="#Top">↑ Back To Top</a>

<p id="Miscellaneous"></>

## Miscellaneous:
```sh

```

<a href="#Top">↑ Back To Top</a>
