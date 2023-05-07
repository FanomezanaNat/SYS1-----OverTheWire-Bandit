# Over The Wire : Bandit
## Introduction

[![N|Solid](https://user-images.githubusercontent.com/53615807/101657981-94eb1e80-3a55-11eb-91c5-55e1a1c93545.png)](https://overthewire.org/wargames/bandit/)



OverTheWire Bandit is a series of capture the flag (CTF) challenges offered by the OverTheWire platform. Bandit is designed for computer security beginners and offers a hands-on, progressive learning experience.


## Missions et objectives

The main objective of Bandit is to introduce users to basic computer security concepts. Each level of Bandit offers a unique scenario where users have to solve security problems using different techniques, such as finding passwords, understanding Unix commands, file manipulation, etc.
So let's begin 😄

## Level 0
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. 
The username is bandit0 and the password is bandit0. 

logging into bandit, using the specific port and username
```sh
 ssh bandit0@bandit.labs.overthewire.org -p 2220
 password:bandit0
```
#### Commands you may need to solve this level
        ssh

## Level 0 → Level 1
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
 Use the command ls to list out your directory. You will find a file named readme. To read the content of the file type in cat readme. The content of the file will be displayed, which is the password for the next level.

```sh
ls 
cat readme
password:NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
#### Commands you may need to solve this level
    ls , cd , cat , file , du , find

## Level 1 → Level 2

The password for the next level is stored in a file called - located in the home directory
Similar to last level, though the file name is ‘ -’. In order to read this file, you will need to reference the file using relative/absolute path since the character ‘-’ may also reference to any parameters of the cat command.


```sh
ls -a
cat ./- or cat <-
password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
#### Commands you may need to solve this level
    ls , cd , cat , file , du , find

## Level 2 → Level 3

The password for the next level is stored in a file called spaces in this filename located in the home directory
Similar to previous levels, the key for next level is available in a file in the home directory. The name of the file is ‘spaces in this filename’. 

```sh
ls
cat spaces\ in\ this\ filename or cat "spaces in this filename"
password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

#### Commands you may need to solve this level
    ls , cd , cat , file , du , find


#### Level 3 → Level 4
The password for the next level is stored in a hidden file in the inhere directory.
Navigate to the inhere directory using cd, list out all files including hidden ones, use the "ls -a"
```sh
ls 
cd inhere
ls -a
cat .hidden
password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
#### Commands you may need to solve this level
    ls , cd , cat , file , du , find

## Level 4 → Level 5

The password for the next level is stored in the only human-readable file in the inhere directory.
To begin this level, login to the bandit server with the username bandit4 and password received from the previous level.
Navigate to the directory inhere found in the home folder using cd. ‘ls’ reveals a list of 10 files all beginning with ‘-file0’ and ending with numbers 0–9. Use file
./ * to know where is the file which is the only human-readable file.

```sh
ls
cd inhere
ls -a 
file ./-*
cat ./file07
password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
#### Commands you may need to solve this level
    ls , cd , cat , file , du , find
    
## Level 5 → Level 6
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
 - human-readable
 - 1033 bytes in size
 - not executable

  Navigate to the inhere directory within the home directory. On listing content, you will find 20 directories, each with a couple of files. The level goal specifies that the file size is 1033 byte. To search for a file of that size use the command below.


```sh
ls 
cd inhere
ls -a
find -type f -size 1033c
password : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
#### Commands you may need to solve this level
    ls , cd , cat , file , find
    
## Level 6 → Level 7
The password for the next level is stored somewhere on the server and has all of the following properties:

 - owned by user bandit7
 - owned by group bandit6
 - 33 bytes in size

To begin this level, login to the bandit server with the username bandit6 and password received from the previous level.
he clue is the user and group ownership info provided. To find a file using group and/or user info, use the find command that i give bellow.

```sh
find / -user bandit7 -group bandit6 -size 33c -print 2>/dev/null | xargs cat
password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
#### Commands you may need to solve this level
    ls , cd , cat , file , find, xargs
    
## Level 7 → Level 8
The password for the next level is stored in the file data.txt next to the word millionth
A file named data.txt can be found in the home directory. If you cat out the file, it contains 98567 lines of data, each beginning with a word followed by a text with 33 characters. To find a single line which contains the word millionth and the key for level 8, cat out the file and pipe the output to grep for the word millionth.
```sh
grep millionth data.txt
password : TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
#### Commands you may need to solve this level
    man, grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
    
## Level 8 → Level 9
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
A file named data.txt could be found in the home directory. If you cat out the file, it contains 1001 lines of data. The level goal specifies that the line of interest occurs only once, which means that there are repeated data. To identify the unique line, just watch the command line that i put bellow ;)

```sh
sort data.txt | uniq -u
password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
### Commands you may need to solve this level
    grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Level 9 → Level 10
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
To begin this level, login to the bandit server with the username bandit9 and password received from the previous level.

A file named data.txt could be found in the home directory. Use the command line bellow
```sh
grep -a == data.txt
password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
### Commands you may need to solve this level
    grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
    
## Level 10 → Level 11
The password for the next level is stored in the file data.txt, which contains base64 encoded data
To begin this level, login to the bandit server with the username bandit10 and password received from the previous level.

A file named data.txt could be found in the home directory. If you cat out the file, you will find the base64 encoded data. To decode use the base64 command with the -d switch. The output reveals the key for level 11.
```sh
base64 -d data.txt
password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

### Commands you may need to solve this level
    grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
#### Helpful Reading Material
    Base64 on Wikipedia
## Level 11 → Level 12
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
Well first I used cat data.txt and it displayed this :
```sh
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
```
As the subject said, all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions,  so I used the site rot13.com to reposition all the letters in their respective places and it give the passwor after rot13.com decode it.
```sh
password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
### Commands you may need to solve this level
    grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
#### Helpful Reading Material
    Rot13 on Wikipedia
    
## Level 12 → Level 13
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

the clues say we need to create a directory under /tmp and use mkdir and we copied the data.txt in the new folder I created and we changed its name.After that  we converted hexadecimal file to his original format.
We now need to find a way to decompress a gzip file this method will use zcat and bcat to decompress zcat will start off compressing and now we will set up a way for " file - " to be linked to read compressed.
After the first compression the output says bzip2 so we must now add bzcat to the extension list.
```sh
mkdir /tmp/folder
cp data.txt /tmp/folder/
mv data.txt compressed.bin
file compressed.bin
xxd -r compressed.bin compressed
zcat compressed | file -
zcat compressed | bzcat | file -
zcat compressed | bzcat | zcat | file -
zcat compressed | bzact | zcat | tar xO | file -
zcat comrpessed | bzcat |zcat | tar xO | tar xO | file -
zcat compressed | bzcat | zcat | tar xO | tar xO |bzcat | file -
zcat compressed | bzcat | zcat | tar xO | tar x | bzcat| tar xO | file -
zcat compressed | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat 
password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

### Commands you may need to solve this level
    grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

#### Helpful Reading Material
    Hex dump on Wikipedia
    
## Level 13 → Level 14
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on.
The objective of this level is to log in into SSH using a SSH key. So we can log in into the next level with that SSH key. And the command line wiil help to log in to bandit14
```sh
ssh -i sshkey.private bandit14@localhost -2220
```
### Commands you may need to solve this level
    ssh, telnet, nc, openssl, s_client, nmap

#### Helpful Reading Material
    SSH/OpenSSH/Keys
## Level 14 → Level 15
To begin this level, login to the bandit server with the username bandit14 and password received from the previous level.

The password of the current level is available in the file /etc/bandit_pass/bandit14. Cat out this file and pipe it’s content to the port 30000 on the localhost using ‘nc’ or ‘netcat’ command. The server should respond with the password for the next level.So to do that write the command line bellow

```sh
cd  /etc/bandit_pass/bandit14
cat bandit14 | nc localhost 30000
password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
### Commands you may need to solve this level
    ssh, telnet, nc, openssl, s_client, nmap

#### Helpful Reading Material
 - How the Internet works in 5 minutes (YouTube) (Not completely accurate, but good enough for beginners)
 - IP Addresses
 - IP Address on Wikipedia
 - Localhost on Wikipedia
 - Ports
 - Port (computer networking) on Wikipedia
  

## Level 15 → Level 16
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption. Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…
To begin this level, login to the bandit server with the username bandit15 and password received from the previous level.

The password of the current level is available in the file /etc/bandit_pass/bandit15. In order to complete this, we need to establish an SSL connection to the local server at port 30001. We also need to pipe the password of the current level to this connection. To do this, use the command as follows:
``` sh
cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001 -ign_eof
password: JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

##  Level 16 → Level 17
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

To begin this level, login to the bandit server with the username bandit16 and password received from the previous level.

Once logged in, use nmap to search for open ports on the local host. You will find 2 ports that are open to connect. As before, the password for the current level is available at /etc/bandit_pass/bandit16. Cat the password out to an SSL connection to the listed ports using the OpenSSL command with the -quiet option. One of the ports will respond with a private key.

Re-run the command and direct the stdout to a new file in a new tmp directory.
Don't forget to copy the rsa privaty key in pvt.key and we'll give the rsa private key to simplify your work:


"-----BEGIN RSA PRIVATE KEY-----

MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=

-----END RSA PRIVATE KEY-----"

```sh
nmap -p 31000-32000 localhost
cat /etc/bandit_pass/bandit16
openssl s_client -connect localhost:31790
cd /tmp
nano pvt.key
chmod 700 pvt.key
ssh bandit17@localhost -i pvt.key -p 2220
```

##  Level 17 → Level 18
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

```sh
diff passwords.new passwords.old
password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```
## Level 18 → Level 19
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

```sh
ssh  bandit18@bandit.labs.overthewire.org -p 2220 "cat ~/readme"
password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Level 19 → Level 20
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

```sh
./bandit20-do cat /etc/bandit_pass/bandit20
password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
## Level 20 → Level 21
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

```sh
echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l localhost 8888 &
ps aux | grep nc
./suconnect 8888
password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

## Level 21 → Level 22
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

```sh
cd /etc/cron.d/
cat cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

## Level 22 → Level 23
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

```sh
cd /etc/cron.d
cat cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

## Level 23 → Level 24
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

```sh
cd /etc/cron.d
cat /usr/bin/cronjob_bandit24.sh
myname=bandit24
cd /var/spool/$myname
mkdir /tmp/john3
chmod 777 /tmp/john3
nano get.sh
chmod +x get.sh
cat /tmp/john3/password.txt
password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
