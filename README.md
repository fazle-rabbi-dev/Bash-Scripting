<img src="bash.png" alt="" />

<p id="top"></>

## 🚨 Introductions:

<details>
<summary>Click Me For Collapse...</summary>

### 🤔 What is Bash?
> In basic terms, Bash is a command line interpreter that typically runs in a text window where user can interpret commands to carry out various actions. The combination of these commands as a series within a file is known as a Shell Script. Bash can read and execute the commands from a Shell Script.

### 🤔 What is Shell?
> Bash scripting is a subset of shell scripting. Shell scripting is a method to automate tasks as a collection of commands. The bash script is one form of shell script. Shells may be one of Korn, C shell, Bourne, Bash, etc

### 🤔 What is Script?
> In computer programming, a script is a program or sequence of instructions that is interpreted or carried out by another program rather than by the computer processor (as a compiled program is).

> A script is sometimes used to mean a list of operating system commands that are prestored in a file and performed sequentially by the operating system's command interpreter whenever the list name is entered as a single command.

</details>


## ⚡ Usages Of Bash :

   *It is used by the System Administrators, Network Engineers, Developers, Scientists, and everyone who use Linux/Unix operating system. They use Bash for system administration, data crunching, web application deployment, automated backups, creating custom scripts for various pages, etc.*

### ⛈️ Topics To Learn In Bash:
* [Variables](#)
* [Operators](#)
* [User input](#)
* [Dates](#)
* `Conditional Statements`
   * [If,else,else if]()
   * [Case]()
* `Loops`
   * [For]()
   * [While]()
   * [Untill]()
* [Functions](#)
* [Arrays](#)
* [Strings](#)
* `Miscellaneous`
   * [Comments]()
   * [Sleep]()
   * [Read File]()
   * [Write File]()
   * [File/Folder Exists or Not]()


---

## Variables
```sh
a=10
b=20
```

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
## User Input:
```sh

```
## Dates:
```sh

```
## Conditional Statements:
```sh

```
## Loops:
```sh

```
## Functions
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

## Strings

```sh
a='Hello'
b='Javatpoint'

result=$a = $b  #   
result=$a != $b #
result=$a \< $b #
result=$a \> $b #
result= -n $str # Zero or greter then Zero
result= -z $str # Zero or Not Zero

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

## Miscellaneous:
```sh

```