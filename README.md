`Note: These notes are for my personal reference!`

# ๐๐๐ฌ๐ก ๐๐๐ซ๐ข๐ฉ๐ญ๐ข๐ง๐  ๐๐ก๐๐๐ญ๐ฌ๐ก๐๐๐ญ

## ๐๐๐ฌ๐ข๐๐ฌ

- Telling interpreter that the file is bash file

```
!#/bin/bash
```

- Make the file executable
```
$ chmod +x script.sh
```

## ๐๐จ๐ฆ๐ฆ๐๐ง๐ญ๐ฌ

```
# this is a single line comment 
```
```
# Multi line comment

# - Method I
<<COMMENTS
  This 
  is a 
  multiline
  comment
COMMENTS

```
```

# - Method II
:'
 This 
  is a 
  multiline
  comment
'

```

## ๐๐๐ซ๐ข๐๐๐ฅ๐๐ฌ

- Syntax: `variable_name=variable_value`
- `Note: There should not be any white spaces on either side of the =`
- `Single quotes (') helps to treat every character as it is`
- `Double quotes (") helps to do the substitution`

---

System Defined Variables | Meaning
--- | ---
`BASH` | represents the Shell Name.
`BASH_VERSION` | specifies the shell version which the Bash holds.
`COLUMNS` | specify the no. of columns for our screen
`HOME` | specifies the home directory for the user
`LOGNAME` | specifies the logging user name.
`OSTYPE` | tells the type of OS.
`PWD` | represents the current working directory.
`USERNAME` | specifies the name of currently logged in user.

```
                                                                                      
#!/bin/bash

echo $BASH
echo $BASH_VERSION
echo $COLUMNS
echo $HOME
echo $LOGNAME
echo $OSTYPE
echo $PWD
echo $USERNAME
                                                                                       
```

---

## ๐๐๐๐๐ข๐ง๐  ๐๐ง๐ฉ๐ฎ๐ญ

- Syntax: `read [flag] varname`
  - `-s` : for silent mode
  - `-p` : for prompt mode
  - `-a` : for arrays

```
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ cat read.sh  
#!/bin/bash

echo "firstname: "
read firstname
echo "lastname: "
read lastname

echo "Hello Mr. $firstname $lastname"

โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ ./read.sh  
firstname: 
shreyas
lastname: 
chavhan
Hello Mr. shreyas chavhan

```


```
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ vim read_prompt.sh
                                                                                       
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ chmod +x read_prompt.sh 
                                                                                       
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ cat read_prompt.sh     
#!/bin/bash

read -p "Your Name: " name

echo "Hello Mr. $name"
                                                                                       
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ ./read_prompt.sh 
Your Name: Shreyas
Hello Mr. Shreyas
                          
```
```
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ vim read_silent.sh
                                                                                       
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ ./read_silent.sh  
Your Password 
Your Password is mypassword, it's secret - don't tell anyone!
                                                                                       
โโโ(shreyasใฟkali)-[~/practise/bash_scripting]
โโ$ cat read_silent.sh 
#!/bin/bash


read -sp "Your Password " password

echo ""
echo "Your Password is $password, it's secret - don't tell anyone!"

```

- Multi-line input

```
while read -r line; do
   printf '%s\n' "$line"
done
```

---


## ๐๐๐ฌ๐ก ๐ข๐-๐๐ฅ๐ข๐-๐๐ฅ๐ฌ๐


- Syntax
```
if [condition]; then
  <blah blah>
elif [condition]; then
  <blah blah>
else
  <blah blah>
fi

```


- `||` : OR
- `&&` : AND

Operators | Description
--- | ---
`! EXPRESSION` | To check if `EXPRESSION` is false.
`-n STRING` | To check if the length of `STRING` is greater than zero.
`-z STRING` | To check if the length of `STRING` is zero (i.e., it is empty)
`STRING1 == STRING2` | To check if `STRING1` is equal to `STRING2`.
`STRING1 != STRING2` | To check if `STRING1` is not equal to `STRING2`.
`INTEGER1 -eq INTEGER2` | To check if `INTEGER1` is numerically equal to `INTEGER2`.
`INTEGER1 -gt INTEGER2` | To check if `INTEGER1` is numerically greater than `INTEGER2`.
`INTEGER1 -lt INTEGER2` | To check if `INTEGER1` is numerically less than `INTEGER2`.
`-d FILE` | To check if `FILE` exists and it is a directory.
`-e FILE` | To check if `FILE` exists.
`-r FILE` | To check if `FILE` exists and the read permission is granted.
`-s FILE` | To check if `FILE` exists and its size is greater than zero (which means that it is not empty).
`-w FILE` | To check if `FILE` exists and the write permission is granted.
`x FILE` | To check if `FILE` exists and the execute permission is granted.

---

## ๐๐๐ฌ๐ก ๐๐๐ฌ๐๐ฌ

- Syntax:
```
#!/bin/bash  
  
echo "Which Operating System are you using?"  
echo "Windows, Android, Chrome, Linux, Others?"  
read -p "Type your OS Name:" OS  
  
case $OS in  
    Windows|windows)  
        echo "That's common. You should try something new."  
        echo  
        ;;  
    Android|android)  
        echo "This is my favorite. It has lots of applications."  
        echo  
        ;;  
    Chrome|chrome)  
        echo "Cool!!! It's for pro users. Amazing Choice."  
        echo  
        ;;  
    Linux|linux)  
        echo "You might be serious about security!!"  
        echo  
        ;;  
    *)  
        echo "Sounds interesting. I will try that."  
        echo  
        ;;  
esac  
```

---

## ๐๐๐ฌ๐ก ๐๐จ๐ซ ๐๐จ๐จ๐ฉ

- C++ like for loop

```
for ((i = 0 ; i < 100 ; i++)); do
  echo $i
done
```

- To read a range
```
for num in {1..10}  
  do  
  echo $num  
done  
```

- a range with increment

```
for num in {1..10..1}  
  do  
  echo $num  
done  
```

- a range with decrement

```
for num in {10..0..1}  
  do  
  echo $num  
done  
```

- Array variables

```
array=(  "element1" "element 2" .  .  "elementN" )  
  
for i in "${arr[@]}"  
  do  
  echo $i  
done  
```

- white spaces in String as word separators

```
#!/bin/bash  
  
for word in $str;  
do  
  <Statements>  
done  
```

- Each line in string as a word

```
#!/bin/bash  
  
for word in "$str";  
  do  
  <Statements>  
done  
```

- Infinite loop

```
i=1;  
for (( ; ; ))  
  do  
  sleep 1s  
  echo "Current Number: $((i++))"  
done  
```
---

## ๐๐๐ฌ๐ก ๐ฐ๐ก๐ข๐ฅ๐ ๐ฅ๐จ๐จ๐ฉ

- C++ Style while loop
```
i=1  
while((i <= 10))  
  do  
  echo $i  
  let i++  
done  
```



## ๐๐ญ๐ก๐๐ซ ๐๐จ๐ญ๐๐ฌ

- Chop off the arithmetic operations to decimal points: `bc <<< "scale=3; $expression"` 
- Round of the arithmetic operation result: `printf %.3f $(echo $expression | bc -l)`
---
> Done
