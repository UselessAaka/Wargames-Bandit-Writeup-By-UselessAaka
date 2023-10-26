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
ls
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
### Flag
>JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
### Approach used
After listing the files we will use 'cat' command with tool 'tr' and keeping values ('A-Za-z' 'N-ZA-Mn-za-m') to use rot13 on the text and get our password.
### Resouces used
use 'man tr' to learn about 'tr' tool and [ROT13 Wikipedia](https://en.wikipedia.org/wiki/ROT13) to learn about rot13.

# Level 12 → Level 13
### Commands used
```
ssh bandit12@bandit.labs.overthewire.org -p 2220
ls
cat data.txt   # We can see that it is a hexdump file.
cd /tmp
mkdir useless1
cd ..
cd ..
cd
cp data.txt /tmp/useless1
cd /tmp/useless1
cat data.txt | xxd -r
cat data.txt | xxd -r > hex
ls
file hex
mv hex hex.gz
ls
gzip -d hex.gz
ls
file hex
mv hex hex.bz2
bzip2 -d hex.bz2
ls
file hex
mv hex hex.gz
gzip -d hex.gz
ls
file hex
tar -xf hex
ls
file data5.bin
tar -xf data5.bin
ls
file data6.bin
tar -xf data6.bin
ls
file data8.bin
mv data8.bin data8.bin.gz
gzip -d data8.bin.gz
ls
file data8.bin
cat data8.bin
```
### Flag
>wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
### Approach used
First I entered the directory 'tmp' then made a file using the 'mkdir' command. Then went back to the the bandit12 folder to get the 'data.txt' file. Using the copy command 'cp', I copied the file to the 'useless1' directory created by me. then used 'cat' command with the tool 'xxd' to reverse engineer the hexdump file and move it to file named 'hex'. After identifying the file type of 'hex', we will see that it is a gzip file which is very similar to zip file in windows which means we just have to extract it. So we rename 'hex' to 'hex.gz' and then use the gzip tool to decompress the 'hex.gz' file. We will again check the file type of the hex file and see that it is a bzip2 file. So we will again rename the file from 'hex' to 'hex.bz2' and then use the bzip2 tool to decompress the file. Again we will check the file type of the hex file and it is gzip again so same process again after that when we check the file type, this time it is a 'tar' file so we will use tar tool with '-xf', where 'x' basically extracts file from archive and 'f' specifies the filename of the archive. We will get a 'data5.bin' file. Again this is a tar file so same step. The we will get 'data6.bin' which a bzip2 file so we will do the same process we did earlier and then again check the file type of the result, which gives us data6.bin file which is in tar format so we will extract it. This time we will get 'data8.bin' file which is in gzip, so we extract it and get an ASCII file named 'data8.bin'. now, we will just read the file and get the password.
### Resources used
manual page of gzip, bzip2, tar, mkdir, [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump) and some videos related to extracting files and making folders.

# Level 13 → Level 14
### Commands used
```
ssh bandit13@bandit.labs.overthewire.org -p 2220
ls
ssh -i sshkey.private bandit14@localhost -p 2220
cat /etc/bandit_pass/bandit14
```
### Flag
>fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
### Approach used
Using 'ls' we will only find one file named 'sshkey.private' which is basically a private key so we will use the ssh tool with '-i' which basically selects a file from which the identity (private key) for public key authentication is read. Also the user will be bandit14 and host name will be localhost as given in question and as always port should be 2220. After connecting to the neww ssh, just use cat command to read the file given in question i.e. /etc/bandit_pass/bandit14. We will get the password.
### Resources used
manual page of ssh and some forums on using keys to connect to ssh.

# Level 14 → Level 15
### Commands used
```
ssh bandit13@bandit.labs.overthewire.org -p 2220
ls
ssh -i sshkey.private bandit14@localhost -p 2220
nc localhost 30000
(put the password from last level only)
```
### Flag
>jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
### Approach used
While doing Level 13 → Level 14 and after reading the password, we can continue from there only and use 'nc' command to connect to localhost using port 30000 and there we need to paste the password from last level to automatically get the next password.
### Resources used
manual page of nc and [The netcat Command in Linux](https://www.tutorialspoint.com/the-netcat-command-in-linux#:~:text=The%20netcat%20command%2C%20also%20known,of%20other%20network%2Drelated%20tasks.)

# Level 15 → Level 16
### Commands used
```
ssh bandit15@bandit.labs.overthewire.org -p 2220
openssl s_client -connect localhost:30001
(Enter the password from last level)
```
### Flag
>JQttfApK4SeyHwDlI9SXGR50qclOAil1
### Approach used
After connecting to the ssh, we use the openssl tool with 's_client' which basically tells the the client wwe need to connect to then we tell about the localhost which is ported to 30001. Then just enter the password from last level to get the password of next level.
### Resources used
manual page of openssl and s_client and the helpful reading material given on OTW site.





