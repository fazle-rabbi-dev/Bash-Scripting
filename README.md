<img src="bash.png" alt="" />

<details>
<summary>Introduction</summary>

### What is bash?
### What is shell?
### What is script?


</details>


### ⚡ Usages Of Bash Scripting :


### 🚨 Topics To Learn In Bash:
#### `Fundamemtals:`
* [Variables](#)
* [Utilities](#)
* [Operators](#)
* [User input](#)
* [Dates](#)
* [Conditional Statements](#)
* [Loops](#)
* [Functions](#)
* [Arrays](#)
* [Strings](#)

#### `Advanced:`
* [Api Calling](#)
* [cURL](#)
* [](#)
* 

<div align="center">

---

Fundamemtals

---

</div>


## **Variables**
```sh
a=10
b=20
```

## **Strings**

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


## -:- **Functions**
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
