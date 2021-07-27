---
description: 'https://tryhackme.com/room/linuxctf'
---

# LinuxCTF - Linux Challenges

## Task 1 Linux Challenges Introduction

### How many visible files can you see in garrys home directory?

```text
garry@ip-10-10-255-137:~$ ls
flag1.txt flag24 flag29
garry@ip-10-10-255-137:~$ ls | wc -l
```

{% hint style="success" %}
3
{% endhint %}

## Task 2 The Basics

### What is flag 1?

```text
garry@ip-10-10-255-137:~$ cat flag1.txt
```

![](../.gitbook/assets/image%20%28263%29.png)

{% hint style="success" %}
f40dc0cff080ad38a6ba9a1c2c038b2c
{% endhint %}

### Log into bob's account using the credentials shown in flag 1.

### What is flag 2?

![](../.gitbook/assets/image%20%28277%29.png)

![](../.gitbook/assets/image%20%28259%29.png)

```text
bob@ip-10-10-255-137:~$ cat flag2.txt
```

{% hint style="success" %}
8e255dfa51c9cce67420d2386cede596
{% endhint %}

### Flag 3 is located where bob's bash history gets stored.

```text
bob@ip-10-10-255-137:~$ cat .bash_history
```

![](../.gitbook/assets/image%20%28272%29.png)

{% hint style="success" %}
9daf3281745c2d75fc6e992ccfdedfcd
{% endhint %}

### Flag 4 is located where cron jobs are created.

```text
bob@ip-10-10-255-137:~$ crontab -e
```

![](../.gitbook/assets/image%20%28265%29.png)

{% hint style="success" %}
dcd5d1dcfac0578c99b7e7a6437827f3
{% endhint %}

### Find and retrieve flag 5.

```text
bob@ip-10-10-255-137:~$ cat $(locate flag5.txt)
```

![](../.gitbook/assets/image%20%28258%29.png)

{% hint style="success" %}
bd8f33216075e5ba07c9ed41261d1703
{% endhint %}

### "Grep" through flag 6 and find the flag. The first 2 characters of the flag is c9.

```text
bob@ip-10-10-177-45:~$ grep 'c9' $(locate flag6.txt)
```

![](../.gitbook/assets/image%20%28279%29.png)

```text
bob@ip-10-10-177-45:~$ grep -o '\w{32}' $(locate flag6.txt)
bob@ip-10-10-177-45:~$ sed -n "/c9/,/ /p" ../flag6.txt
```

{% hint style="success" %}
 c9e142a1e25b24a837b98db589b08be5
{% endhint %}

### Look at the systems processes. What is flag 7.

```text
bob@ip-10-10-99-145:~$ ps -aef |grep flag
```

![](../.gitbook/assets/image%20%28268%29.png)

{% hint style="success" %}
274adb75b337307bd57807c005ee6358
{% endhint %}

### De-compress and get flag 8.

```text
bob@ip-10-10-99-145:~$ tar -xvzf flag8.tar.gz flag8.txt
bob@ip-10-10-99-145:~$ cat flag8.txt 
```

{% hint style="success" %}
75f5edb76fe98dd5fc9f577a3f5de9bc
{% endhint %}

### By look in your hosts file, locate and retrieve flag 9.

```text
bob@ip-10-10-99-145:~$ tail -n 1 /etc/hosts
```

> 127.0.0.1 dcf50ad844f9fe06339041ccc0d6e280.com

{% hint style="success" %}
dcf50ad844f9fe06339041ccc0d6e280
{% endhint %}

### 10 Find all other users on the system. What is flag 10.

```text
bob@ip-10-10-99-145:~$ cat /etc/passwd
```

> 5e23deecfe3a7292970ee48ff1b6d00c:x:1002:1002:,,,:/home/5e23deecfe3a7292970ee48ff1b6d00c:/bin/bash

{% hint style="success" %}
5e23deecfe3a7292970ee48ff1b6d00c
{% endhint %}

## Task 3 Linux Functionality

### Run the command flag11. Locate where your command alias are stored and get flag 11.

```text
bob@ip-10-10-99-145:~$ cat .bashrc |grep flag11
```

> alias flag11='echo "You need to look where the alias are created..."' \#b4ba05d85801f62c4c0d05d3a76432e0

{% hint style="success" %}
b4ba05d85801f62c4c0d05d3a76432e0
{% endhint %}

###  Flag12 is located were MOTD's are usually found on an Ubuntu OS. What is flag12?

```text
bob@ip-10-10-99-145:~$ cat /etc/update-motd.d/00-header |grep Flag12
```

> \# Flag12: 01687f0c5e63382f1c9cc783ad44ff7f

{% hint style="success" %}
01687f0c5e63382f1c9cc783ad44ff7f
{% endhint %}

### Find the difference between two script files to find flag 13.

```text
bob@ip-10-10-99-145:~$ cd flag13/ 
bob@ip-10-10-99-145:~/flag13$ dir
script1 script2 
bob@ip-10-10-99-145:~/flag13$ diff script1 script2
```

![](../.gitbook/assets/image%20%28271%29.png)

{% hint style="success" %}
3383f3771ba86b1ed9ab7fbf8abab531
{% endhint %}

### Where on the file system are logs typically stored? Find flag 14.

```text
tail -n 1 /var/log/$(ls /var/log/ |grep flag)
```

{% hint style="success" %}
71c3a8ad9752666275dadf62a93ef393
{% endhint %}

### Can you find information about the system, such as the kernel version etc.

### Find flag 15.

```text
bob@ip-10-10-99-145:~/flag13$ cat /etc/lsb-release
```

![](../.gitbook/assets/image%20%28267%29.png)

{% hint style="success" %}
a914945a4b2b5e934ae06ad6f9c6be45
{% endhint %}

### Flag 16 lies within another system mount.

```text
bob@ip-10-10-99-145:~$ cd /media/f/l/a/g/1/6/is/cab4b7cae33c87794d82efa1e7f834e6/
```

{% hint style="success" %}
cab4b7cae33c87794d82efa1e7f834e6
{% endhint %}

### Login to alice's account and get flag 17. Her password is TryHackMe123

```text
bob@ip-10-10-99-145:~$ ssh alice@localhost
alice@ip-10-10-99-145:~$ cat flag17 
```

{% hint style="success" %}
89d7bce9d0bab49e11e194b54a601362
{% endhint %}

### Find the hidden flag 18.

```text
alice@ip-10-10-99-145:~$ cat .flag18
```

{% hint style="success" %}
c6522bb26600d30254549b6574d2cef2
{% endhint %}

### Read the 2345th line of the file that contains flag 19.

```text
alice@ip-10-10-99-145:~$ awk 'NR==2345' flag19
alice@ip-10-10-99-145:~$ sed '2345!d' flag19 
```

{% hint style="success" %}
490e69bd1bf3fc736cce9ff300653a3b
{% endhint %}

## Task 4 Data Representation, Strings and Permissions

### Find and retrieve flag 20.

```text
alice@ip-10-10-71-95:~$ cat $(locate flag20) |base64 -d 
```

{% hint style="success" %}
02b9aab8a29970db08ec77ae425f6e68
{% endhint %}

### Inspect the flag21.php file. Find the flag.

```text
alice@ip-10-10-129-13:~$ cat $(locate flag21.php)
alice@ip-10-10-129-13:~$ less $(locate flag21.php)
```

![](../.gitbook/assets/image%20%28283%29.png)

{% hint style="success" %}
g00djob
{% endhint %}

### Locate and read flag 22. Its represented as hex.

```text
alice@ip-10-10-71-95:~$ cat flag22 |xxd -r -p
```

{% hint style="success" %}
 9d1ae8d569c83e03d8a8f61568a0fa7d
{% endhint %}

### Locate, read and reverse flag 23.

```text
alice@ip-10-10-71-95:~$ cat $(locate flag23) |rev
```

{% hint style="success" %}
ea52970566f4c090a7348b033852bff5
{% endhint %}

### Analyse the flag 24 compiled C program. Find a command that might reveal human readable strings when looking in the source code.

```text
alice@ip-10-10-71-95:~$ strings $(locate flag24) |grep flag
```

{% hint style="success" %}
hidd3nStr1ng
{% endhint %}

### Flag 25 does not exist.

{% hint style="success" %}
No answer needed
{% endhint %}

### Locate and retrieve flag 26.

```text
find / -xdev -type f -print0 2>/dev/null | xargs -0 grep -E '^[a-z0-9]{32}$' 2>/dev/null
alice@ip-10-10-71-95:~$ cat /var/cache/apache2/mod_cache_disk/config.json
```

![](../.gitbook/assets/image%20%28281%29.png)

{% hint style="success" %}
4bceb76f490b24ed577d704c24d6955d
{% endhint %}

### Locate and retrieve flag 27, which is owned by the root user.

```text
locate flag27
sudo -l
sudo /bin/cat /home/flag27
```

![](../.gitbook/assets/image%20%28282%29.png)

{% hint style="success" %}
6fc0c805702baebb0ecc01ae9e5a0db5
{% endhint %}

### Whats the linux kernel version?

```text
alice@ip-10-10-71-95:~$ uname -r
4.4.0-1075-aws
```

{% hint style="success" %}
4.4.0-1075-aws
{% endhint %}

### Find the file called flag 29 and do the following operations on it:

Remove all spaces in file. Remove all new line spaces. Split by comma and get the last element in the split.

```text
alice@ip-10-10-71-95:~$ cat $(locate flag29) | tr -d ' ' | tr -d '\n' |awk -F',' '{print $NF}'
fastidiisuscipitmeaei
alice@ip-10-10-71-95:~$ cat $(locate flag29) | tr -d ' ' | tr -d '\n' |awk -F',' '{print $NF}' |grep -E "[0-9a-z]"
```

{% hint style="success" %}
fastidiisuscipitmeaei
{% endhint %}

## Task 5 SQL, FTP, Groups and RDP

### Use curl to find flag 30.

```text
alice@ip-10-10-71-95:~$ curl localhost
flag30:fe74bb12fe03c5d8dfc245bdd1eae13f
```

{% hint style="success" %}
fe74bb12fe03c5d8dfc245bdd1eae13f
{% endhint %}

### Flag 31 is a MySQL database name.

> MySQL username: root
>
> MySQL password: hello

```text
alice@ip-10-10-71-95:~$ mysql -u root -p 
Enter password:
Welcome to the MySQL monitor.
Commands end with ; or \g.
Your MySQL connection id is 6 Server version: 5.7.25-0ubuntu0.16.04.2 (Ubuntu)
Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.
Oracle is a registered trademark of Oracle Corporation and/or its affiliates.
Other names may be trademarks of their respective owners.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
mysql> show databases;
+-------------------------------------------+
| Database |
+-------------------------------------------+
| information_schema |
| database_2fb1cab13bf5f4d61de3555430c917f4 |
| mysql |
| performance_schema |
| sys |
+-------------------------------------------+
5 rows in set (0.00 sec)
```

{% hint style="success" %}
2fb1cab13bf5f4d61de3555430c917f4
{% endhint %}

### Bonus flag question, get data out of the table from the database you found above!

```text
mysql> use database_2fb1cab13bf5f4d61de3555430c917f4 
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed mysql> show tables; 
+-----------------------------------------------------+ 
| Tables_in_database_2fb1cab13bf5f4d61de3555430c917f4 |
+-----------------------------------------------------+
| flags |
+-----------------------------------------------------+
1 row in set (0.00 sec)

mysql> select * from flags; 
+----+----------------------------------+
| id | flag | +----+----------------------------------+
| 1 | ee5954ee1d4d94d61c2f823d7b9d733c |
+----+----------------------------------+
1 row in set (0.00 sec)
```

{% hint style="success" %}
ee5954ee1d4d94d61c2f823d7b9d733c
{% endhint %}

### Using SCP, FileZilla or another FTP client download flag32.mp3 to reveal flag 32.

```text
scp alice@10.10.71.95:flag32.mp3 . 
alice@10.10.71.95's password: 
flag32.mp3 100% 10KB 196.7KB/s 00:00
audacity flag32.mp3
```

{% hint style="success" %}
tryhackme1337
{% endhint %}

### Flag 33 is located where your personal $PATH's are stored.

```text
bob@ip-10-10-71-95:~$ head -n 1 .profile
Flag 33: 547b6ceee3c5b997b625de99b044f5cf
```

{% hint style="success" %}
547b6ceee3c5b997b625de99b044f5cf
{% endhint %}

### Switch your account back to bob. Using system variables, what is flag34?

```text
bob@ip-10-10-71-95:~$ printenv |grep flag 
flag34=7a88306309fe05070a7c5bb26a6b2def
```

{% hint style="success" %}
7a88306309fe05070a7c5bb26a6b2def
{% endhint %}

### Look at all groups created on the system. What is flag 35?

```text
bob@ip-10-10-71-95:~$ cat /etc/group |grep flag
flag35_769afb6:x:1005:
bob@ip-10-10-71-95:~$ getent group |grep flag
flag35_769afb6:x:1005:
```

{% hint style="success" %}
769afb6
{% endhint %}

### Find the user which is apart of the "hacker" group and read flag 36.

```text
bob@ip-10-10-71-95:~$ locate flag36 /etc/flag36
bob@ip-10-10-71-95:~$ ls -lah /etc/flag36
-rw-r----- 1 root hacker 33 Feb 19 2019 /etc/flag36 
bob@ip-10-10-71-95:~$ cat /etc/group |grep hacker hacker:x:1004:bob 
bob@ip-10-10-71-95:~$ cat /etc/flag36 
83d233f2ffa388e5f0b053848caed1eb
```

{% hint style="success" %}
83d233f2ffa388e5f0b053848caed1eb
{% endhint %}

### Well done! You've completed the LinuxCTF room!

{% hint style="success" %}
No answer needed
{% endhint %}

