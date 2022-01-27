
> ## __Hey it's me__  **___Rj Raju___**

# __Bash Scripting Notes__
## **Types of Shell?**

----------

-   `Bourne Shell`: was developed by `Stephen Bourne`, it came with the first version of `Unix`. By using `sh` command we can access this Shell.
-   `Bash Shell`: Bash for Bourne Again SHell. It is an advanced version of Bourne Shell (sh), this is the default Shell for the most linux distributions, by using `bash` command, we can access this Shell.
-   `Korn Shell`: developed by David Korn, mostly used in IBM AIX OS, by using `ksh` command, we can access this Shell.
-   `Cshell`, `TShell`,`ZShell`, …
* sh      ( bash shell )
* bash    ( born again shell )
* cshell
* Tshell
* zsh     ( Zshell )
* tmux    ( Tmux )
___
# Chapter -1 Introduction & shebang

* file management (update , backup , clear , automating task's)
* extension is ( .sh )
* #!/bin/sh ( shabang , interpreter )
* #!/bin/bash ( shebang , interpreter )
* #!/bin/zsh ( shabang , interpreter )
* " ./ " ( use specified interpreter )
* chmod +x code.sh ( give executive permis.. )
* ex: ./code.sh

```bash
echo " HELLO WORLD "
```
```
output : HELLO WORLD
```
```bash
printf " Helllo "
```
```
output : Hello
```
```bash
#!/bin/bash
echo " HELLO WORLD This is the first shell script "
```
___

# Chapter -2 Variables

* What is Variable ? 
**variable is a simpley storage location with a specifiication name**
* no spaces before & after equal sign

```bash
#!/bin/bash
NAME="Raju"
echo "MyName is $NAME"
```
```
output : MyName is Raju
```
```bash
#!/bin/bash
NAME="Raju"
SPORT="Foot"
echo "The most popular sport is ${SPORT}ball"
```
```
output : The most popular sport is Football
```
___

# Chapter -3 User Input

* read  ` -p ` ( prompt )

```bash
#!/bin/bash
read -p "Enter Your Name : " NAME
echo "Your name is $NAME"
Enter Your Name :
raju
```
```
output : Your name is raju"
```
```bash
#!/bin/bash
echo "Please Enter your full name : "
read FNAME LNAME
echo "Your Name is $FNAME $LNAME"
```
```
output: Please Enter your full name :
Rj Raju
Your Name is Rj Raju
```

```bash
#!/bin/bash
echo "Please Enter your name and your age : "
read NAME AGE
echo "Your Name is $NAME and your age is $AGE"
```
```
output: Please Enter your full name :
Raju 20
Your Name is Raju and your age is 20
```
### My Test Script

```bash
#!/bin/bash
echo -e "\e[1;31m -----EVIL_CORP----- \e[0m"
read -p "Enter Your First Name: " FNAME
read -p "Emter Your Last Name : " LNAME
read -p "Enter Your Age : " AGE
read -p "Enter Your Birth Year " YEAR
echo "Your Name is $FNAME $LNAME And Your $AGE Old And You Born In $YEAR Year"
echo -e "\e[1;31m Thank You ! \e[0m"
```
___
# Chapter -4 if & if/else
```
#!/bin/bash
if [condition];
then
    statements
fi
```
```bash
#!/bin/bash
NAME="Raju"
if [[ "$NAME" = "Raju" ]]; then
    echo "Welcome! Rj"
fi
```

```bash
#!/bin/bash
echo "Please Enter your username"
read NAME
if [ "$NAME" = "Elliot" ];
then
    echo "Welcome Elliot"
    else
    echo "Invali User Name"
fi
```
### My Test Script

```bash
#!/bin/bash
echo ""
echo "----- WELCOME ----- "
sleep 2
echo ""
read -p "Enter Your Name : " Name
if [[ "$Name" = Raju ]];
then
    sleep 2
    echo "Welcome $Name"
    else
    sleep 2
    echo "Invalid User"
    echo "----- Thank You ----- "
fi
```

```bash
#!/bin/bash

clear
echo ""
sleep 3
echo "---------- Welcome to Evil-Corp ----------"
echo ""
sleep 2
echo "Submit Your Details"
echo ""
sleep 1
read -p "Your First Name : " Fname
read -p "Your Last Name  : " Lname
read -p "Your Age        : " Age
echo ""
sleep 2
echo "Processing ..."
echo ""
sleep 5
echo "$Fname $Lname regester successfully ."
echo ""
sleep 3
if [[ "$Fname" = "raju" ]] || [[ "$Lname" = "raju" ]] || [[ "$Fname" = "Raju" ]] || [[ "$Lname" = "Raju" ]] ; then
    echo "Welcome back Rj !"
fi
echo ""
echo "---------- Thank you ----------"
```

# Chapter -5 Test Scripts

```bash
#!/bin/bash
if [ -d /usr/share/wordlists ];
then
    echo "Yes it Exists"
else
    echo "the file dosnt exist"
fi
```

```bash
#!/bin/bash
if [ -e /usr/share/wordlists/rockyou.txt ];
then
    echo "Yes it Exists"
else
    echo "the file dosnt exist"
fi
```

```bash
#!/bin/bash
if [ -e /etc/shadow ];
then
    echo "Yes it Exists"
else
    echo "the file dosnt exist"
fi
```

## Write a script to find the greater of two numbers:

* `-gt` is a greater sign

```bash
#!/bin/bash
echo " "
read -p " Enter first number : " A
read -p " Enter second number : " B
if [[ $A -gt $B ]]; then
    echo " first number is greater than second"
elif [[ $A -lt $B ]]; then
        echo " second number is greater than first"
    else
        echo " both numbers are equal "
fi
```

## Write a script to find the greater of three numbers:
* **Note** : the use of the `-a` in the a condition, it performs the AND logical operation, `-o` for the logical or operation, `!` for logical not.
```bash
#!/bin/bash
read -p " 1 : " a
read -p " 2 : " b
read -p " 3 : " c
if [ $a -gt $b -a $a -gt $c ]; then
    echo " 1 greater"
 elif [ $b -gt $c ]; then
        echo " 2 is grater"
    else
        echo "3 is bigger"
 fi
 ```

## Question3: Write a script to find if a given number is even or not:

```bash
#!/bin/bash
read -p " Enter any number : " NUMBER
if [[ $[$NUMBER%2] -eq 0 ]]; then
    echo " The Number $NUMBER is even "
else
    echo " The Number $NUMBER is odd "
fi
```
## File Test Options

* **NOTE** : The `-e` option return true if a given file/directory exists.

```bash
#!/bin/bash
if [[ -e /etc/passwd ]]; then
    cat /etc/passwd
    else
        echo " not exists"
fi
```
---

* The `-f` option returns true if a given file is a regular file.
* The `-d` option returns true if a given file is a directory.
* The `-s` option returns true if a given file is not empty, -s for size.
* The `-l` option returns true if a given file is a link file.
* The `-b` option returns true if a given file is a block special file.
* The `-c` option returns true if a given file is a character special file.
* The `-r` option returns true if the current user has read permiision on the  given file.
* The `-w` option returns true if the current user has write permiision on the given file.
* The `-x` option returns true if the current user has execute permiision on the given file.
* The `-o` option returns true if the current user is the owner of the given file.
* file1 `-ot` file2 returns true if file1 is oltder than file2 (last modified time).
* file1 `-nt` file2 returns true if file1 is newer than file2 (last modified time).
* The `-z` option returns true if a given string is empty.

---

## Write a script to test whether a given file is regular file or directory:

```bash
#! /bin/bash
echo " "
read -p " Enter file/dir name : " NAME
if [[ -e $NAME ]]; then
    if [[ -f $NAME ]]; then
        echo " it is a file "
    elif [[ -d $NAME ]]; then
            echo " it is folder "
        else
            echo " it is somthing "
    fi
else
    echo " not found :( "
fi
```

## Write script to comapre two files

```bash
#!/bin/bash
  read -p "enter the first file name : " file1
  read -p "enter the second file name : " file2
  result=$(cmp $file1 $file2)
  if [[ -z "$result" ]]; then
    echo "they are same"
  else  
    echo "they are not"
  fi
```
---

### String test options

* `str1` = `str2` returns true if both strings are equal.
* `str1` != `str2` returns true if both strings are not equal.
* `-z` `str1` returns true if `str1` is empty.
* `-n` `str1` returns true if `str1` is not empty.
* `str1` > `str2` returns true if `str1` is alphabitically greater than  `str2`.
* `str1` < `str2` returns true if `str1` is alphabitically lesser than `str2`.
* **Note** that the symbol `<` is also a redirection symbol, so we should use the backslach `str1 \< str2`
* `[ 0 ]`, `[ 1 ]` returns true all the time.

---

# Chapter -6 Functions

## print your name using functions

```bash
#!/bin/bash
name () {
    read -p " Enter Your Name : " N
    echo " Your Name is : $N"
    return
}
name
```
---

## full-update

```bash
#!/bin/bash
fullupdate () {
    clear
    echo " Update started ... "
    sudo apt-get update -y
    sudo apt-get dist-update -y
    sudo apt-get autoremove -y
    echo " Update completed :) "
}
fullupdate
```
---
## My Test Script
```bash
#!/bin/bash
sinup(){
    clear
    echo ""
    echo " -------------------- Welcome -------------------- "
    echo ""
    sleep 2
    read -p " Enter Your Name       :  " name
    read -p " Enter Your Age        :  " age
    read -p " Enter Your Email-ID   :  " email
    echo ""
    echo " Processing ... "
    sleep 5
    echo ""
    echo " ---------------------------------------------------"
    echo ""
    echo " Here is your details you entered "
    echo " Your name is       :   $name"
    echo " Your age is        :   $age"
    echo " Your Email-ID is   :   $email"
    echo ""
    echo " Thank you :) "
    echo ""
    echo " ---------------------------------------------------"
    echo ""
}
sinup
```
### output
```
 -------------------- Welcome -------------------- 

 Enter Your Name       :  Elliot
 Enter Your Age        :  40
 Enter Your Email-ID   :  test@test.com

 Processing ... 

 ---------------------------------------------------

 Here is your details you entered 
 Your name is       :   Elliot
 Your age is        :   40
 Your Email-ID is   :   test@test.com

 Thank you :) 

 ---------------------------------------------------

```
---
```bash
#!/bin/bash
myinstall(){
    clear
    echo ""
    echo "Installling ..." | lolcat
    echo ""
    sleep 3
    sudo apt-get -y install zsh
    sudo apt-get -y install sl
    sudo apt-get -y install lolcat
    sudo apt-get -y install figlet
    sudo apt-get -y install htop
    sudo apt-get -y install tmux
    sudo apt-get -y install cmatrix
    sudo apt-get -y install glances
    sudo apt-get -y install whowatch
    sudo apt-get -y install python
    sudo apt-get -y install python3
    sudo apt-get -y install apache2
    sudo apt-get -y install wine
    sudo dpkg --add-architecture i386 && sudo apt-get update && sudo apt-get install wine32
    echo ""
    echo "Completed :) " | lolcat
    echo ""
    return
}
myinstall
``` 
---

## create a loading screen

```bash
#!/bin/bash

load(){
        echo -ne '#####                     (33%)\r'
        sleep 1
        echo -ne '#############             (66%)\r'
        sleep 1
        echo -ne '#######################   (100%)\r'
        echo -ne '\n'
        return
}
load
```
---

## simple script :)

```bash
#!/bin/bash

banner(){
    echo ""
    echo " -----------------------"
    echo "  Welcome To Evil-Corp"
    echo " -----------------------"
    echo ""
}

load(){
    echo -ne ' #####                     (33%)\r'
    sleep 1
    echo -ne ' #############             (66%)\r'
    sleep 1
    echo -ne ' #######################   (100%)\r'
    echo -ne '\n'
    return
}

banner
sleep 1
echo " Enter Your Details"
echo ""
read -p " Enter Your Name : " NAME
sleep 1
read -p " Enter Your Age  : " AGE
echo ""
sleep 1
echo " Loading ..."
load
sleep 1
echo ""
echo " -----------------------"
echo "  Your Name is : $NAME"
echo "  Your Age is  : $AGE"
echo " -----------------------"
echo ""
```
---

## Chapter -7  While Loop

```
while [ condition ]
do
  body
done
```
---

### 

```bash

#!/bin/bash

i=0   
while [ $i -le 9 ]
do
  echo $i
  sleep 2          
  let i++
done
```

### output

```
$ ./code.sh 
0
1
2
3
4
5
6
7
8
9
```
## Display time every second
```bash
#!/bin/bash

while [ true ] 
do
  clear
  echo -e "\n\n\n\n$(date +%H:%M:%S)"
  sleep 1
done
```
* The -e option to process the scape characters like \n, we can replace echo -e by printf "\n\n\n\n$(date +%H:%M:%S)"

### output
```
07:21:16
```
---
## simple while loop

```bash
#!/bin/bash

while [[ true ]]; do
    echo "Linux is best :)"
done
```
## output

```
Linux is best :)
Linux is best :)
Linux is best :)
Linux is best :)
Linux is best :)
Linux is best :)
Linux is best :)
.
.
.
```
---

# :(){ :|: & };:

> ## _To be continued ..._



