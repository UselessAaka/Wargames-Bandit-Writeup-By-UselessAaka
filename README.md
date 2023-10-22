# Wargames-Bandit-Writeup
Writeups for bandit wargames levels

# Level 0
### Commands used
`ssh bandit0@bandit.labs.overthewire.org -p 2220 `
### Flag
> bandit0
### Resources used
[SSH wikipedia](https://en.wikipedia.org/wiki/Secure_Shell) to get more knowledge about it and '[How to use SSH on wikiHow](https://www.wikihow.com/Use-SSH)' to learn how to use a ssh.

# Level 0 → Level 1
### Commands used
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
ls -a
cat readme
exit
```
* Note that exit will be used in every level.
### Flag
> NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
### Approach used
First I connected to the ssh using the password we got from last level then used 'ls -a' to list all the files. After that I used the command ' cat readme' to read the contents of the file 'readme' and there I got the password for level 2.

* Note that password will be used from last level to connect to the ssh everytime.

# Level 1 → Level 2
### Commands used
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
ls -a
cat ./-
```

### Flag
> rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
### Approach used 
After connecting to the ssh and listing the files I used the command 'cat ./-' to read contents of hyphen file and there we got the next password. 

# Level 2 → Level 3
### Commands used
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
ls -a
cat spaces\ in\ this\ filename
```
### Flag 
>aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
### Approach used
After connecting to the ssh and listing the files I used the command 'cat spaces\ in\ this\ filename ' to read contents of the file and there we got the next password.

# Level 3 → Level 4
### Commands used 
```
ssh bandit3@bandit.labs.overthewire.org -p 2220
ls -alps
cd inhere/
ls -a
cat .hidden
```

### Flag
>2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
### Approach used
After connecting to ssh, we have to go inside a directory named 'inhere/'. Now type the next command 'ls -alps' which will give us all files in a list form also apply slash(/) in front of the directories. Inside the directory you will see a file named '.hidden' and we have to read this to get the next password.

# Level 4 → Level 5
### Commands used
```
ssh bandit4@bandit.labs.overthewire.org -p 2220
ls 
cd inhere/
ls
file ./-file00
.
.
.
.
file ./-file09
cat ./-file07
```
 **OR**
 ```
ssh bandit4@bandit.labs.overthewire.org -p 2220
ls 
cd inhere/
ls
file ./*
cat ./-file07
```
### Flag 
>lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
### Approach used 
After connecting to the ssh I entered the 'inhere' directory then listed all the files. In the first method I have to check file type for every file by using ' file ./-fileXX' again and again which is very time consuming to do instead of doing that I used the second method through which I can see the file type of every file in the directory by just using one command ' file ./*'. Then I just used 'cat' command to read the 'ASCII text' file that is the file '-file07' to get the password.
### Resources used
[phoenixNAP](https://phoenixnap.com/kb/linux-file-command) and file command from '[Commands you may need to solve this level](https://man7.org/linux/man-pages/man1/file.1.html)'

# Level 5 → Level 6
### Commands used
```
ssh bandit5@bandit.labs.overthewire.org -p 2220
ls 
cd inhere/
ls
find . -size 1033c -readable ! - executable
cat ./maybehere07/.file2
```
### Flag
>P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
### Approach used
After entering the 'inhere' directory we will 20 more directories named from 'maybehere00' to 'maybehere19'. Now I used the find command to find a file which is human readable, not executable(used '!' for not) with keeping the size 1033c as given in the question, which gave me the output './maybehere07/.file2'. Then I just used the 'cat' command on this file to get the password.
### Resources used
find command from '[Commands you may need to solve this level](https://man7.org/linux/man-pages/man1/find.1.html)'

#  Level 6 → Level 7
### Commands used 
```
ssh bandit6@bandit.labs.overthewire.org -p 2220
find / -user bandit7 -group bandit6 -size 33c
cat /var/lib/dpkg/info/bandit7.password
```
### Flag
>z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
### Approach used
After connecting to the server we will just use the find command to find a file with user name 'bandit7' and in group 'bandit6' with a size of 33 bytes. We will get a big list of files and we just need to find a location where ' permission denied' is not written. On searching we will find '/var/lib/dpkg/info/bandit7.password' which has nothing written in front or back of it, so we will just use 'cat' command to read this file and get the password.
# Level 7 → Level 8
### Commands used
```
ssh bandit7@bandit.labs.overthewire.org -p 2220
ls
cat data.txt | grep "millionth"
```
### Flag
>TESKZC0XvTetK0S9xNwm25STk5iWrBvP
### Approach used
After using 'ls' command we will get only one file named 'data.txt'. Now by using 'cat' and 'grep' command together, we will find the word 'millionth' and the password is written in front of it.
### Resources used
learnt about grep from [Grep Command in Linux ](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=grep%20is%20short%20for%20%22global,a%20powerful%20command%20to%20use.) or use the command 'man grep' to know more about grep.

# Level 8 → Level 9
### Commands used
```
ssh bandit8@bandit.labs.overthewire.org -p 2220
ls
cat data.txt | sort | uniq -c
```
### Flag
>EN632PlfYiZbn3PhVK3XOGSlNInNE00t
### Approach used
After listing the files we find the file ' data.txt'. Now we use 'cat' to read the file with using commands like 'sort' to sort the identical texts and 'uniq -c' to to sort all texts with no. of counts they have appeared. We will find only 1 text that has appeared once so that is the password.
### Resource used
we can use commands 'man sort' and 'man uniq' to know more about them in the terminal itself.

# Level 9 → Level 10
### Commands used
```
ssh bandit9@bandit.labs.overthewire.org -p 2220
ls
strings data.txt | grep =
```
### Flag
>G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
### Approach used
We can't use the 'cat' command here cause this is not a human readable file, so instead we are using the ' strings' command to use it to find readable strings and also using the 'grep' command to find text with '='. We will find two texts with equal to in front of them and one of them is the password.
### Resources used
we can learn about 'strings' command from '[Linux strings command](https://www.javatpoint.com/linux-strings-command)'

# Level 10 → Level 11
### Commands used
```
ssh bandit10@bandit.labs.overthewire.org -p 2220
ls
cat data.txt | base64 -d      or   base64 data.txt -d
```
### Flag
>6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
### Approach used
When we use ' cat data.txt' we can easily see that the file is in base64 because the text is ending with two '='(which tells us that it is base64). So now we have to use 'cat' with the tool base64 and using '-d' to decode it and get the password.
### Resources used 
using the command ' man base64'.

# Level 11 → Level 12
### Commands used
```
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
### Flag
>
### Approach used



