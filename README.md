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



