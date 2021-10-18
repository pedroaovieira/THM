---
description: https://tryhackme.com/room/linux3
---

# Linux Fundamentals Part 3

## Task 1 Intro

### Read the above.

{% hint style="success" %}
No answer needed
{% endhint %}

### Deploy the machine attached to this task!

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 \[Section 5: Advanced File Operations] - cp

cp duplicates(copies) files. The syntax is  `cp <file> <destination>`&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 \[Section 5: Advanced file Operations] - cd && mkdir

Linux allows you to change the location of the current directory through the use of the cd command. The syntax of the cd command is this, `cd <directory>`.

This brings us to mkdir, occasionally you'll want to make a new directory to store files in, and that is done using mkdir, the syntax of mkdir is `mkdir <directory name>`.

### &#x20;Using relative paths, how would you cd to your home directory.

{% hint style="success" %}
cd \~
{% endhint %}

### Using absolute paths how would you make a directory called test in /tmp

{% hint style="success" %}
mkdir /tmp/test
{% endhint %}

## Task 4 \[Section 5: Advanced File Operations] ln

The ln syntax is `ln source destination`.

The syntax for a symbolic link is the exact same, but it uses the -s flag, so to create a symbolic link, you would run `ln -s <file> <destination>`.

### How would I link /home/test/testfile to /tmp/test

{% hint style="success" %}
ln /home/test/testfile /tmp/test
{% endhint %}

## Task 5 \[Section 5 - Advanced File Operations]: find

The true power of this command though comes from the parameters you can provide it. You can use `find dir -user` , to list every file owned by a specific user; you can use `find dir -group` to list every file owned by a specific group.

### How do you find files that have specific permissions?

{% hint style="success" %}
\-perm
{% endhint %}

### How would you find all the files in /home

{% hint style="success" %}
find /home
{% endhint %}

### How would you find all the files owned by paradox on the whole system

{% hint style="success" %}
find / -user paradox
{% endhint %}

## Task 6 \[Section 5: Advanced File Operations] - grep

`grep <regular expression> <file>`

### What flag lists line numbers for every string found?

{% hint style="success" %}
\-n
{% endhint %}

### How would I search for the string boop in the file aaaa in the directory /tmp

{% hint style="success" %}
grep boop /tmp/aaaa
{% endhint %}

## Task 7 Binary - Shiba3

### What is shiba4's password

{% hint style="success" %}
test1234
{% endhint %}

## Task 8 \[Section 6: Miscellaneous]: Intro

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 9 \[Section 6: Miscellaneous]: sudo

sudo is Linux's run as administrator button, and the syntax goes `sudo <command>`.

### How do you specify which user you want to run a command as.

{% hint style="success" %}
\-u
{% endhint %}

### How would I run whoami as user jen?

{% hint style="success" %}
sudo -u jen whoami
{% endhint %}

### How do you list your current sudo privileges(what commands you can run, who you can run them as etc.)

{% hint style="success" %}
\-l
{% endhint %}

## Task 10 \[Section 6: Miscellaneous]: Adding users and groups

The syntax for both of these commands are `adduser username` and `addgroup groupname`.

### How would I add the user test to the group test

{% hint style="success" %}
sudo usermod -a -G test test
{% endhint %}

## Task 11 \[Section 6: Miscellaneous]: nano

nano is a terminal based text editor. The syntax for nano is `nano <file you want to write to>`

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 12 \[Section 6: Miscellaneous]: Basic shell scripting

```
#!/bin/bash
echo hello
echo whoami
whoami
```

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 13 \[Section 6: Miscellaneous]: Important Files and Directories

* /etc/passwd - Stores user information - Often used to see all the users on a system
* /etc/shadow - Has all the passwords of these users
* /tmp - Every file inside it gets deleted upon shutdown - used for temporary files
* /etc/sudoers - Used to control the sudo permissions of every user on the system
* /home - The directory where all your downloads, documents etc are.
* /root - The root user's home directory
* /usr - Where all your software is installed
* /bin and /sbin - Used for system critical files
* /var - The Linux miscellaneous directory, a myriad of processes store data in /var
* $PATH - Stores all the binaries you're able to run

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 14 \[Section 6 - Miscellaneous]: Installing packages(apt)

`apt install package`

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 15 \[Section 6: Miscellaneous]: Processes

A list of user created processes can be viewed with the `ps` command

&#x20;To view a list of all system processes, you have to use the `-ef` flag

The syntax of kill is `kill <PID>`.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}
