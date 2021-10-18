---
description: https://tryhackme.com/room/linux2
---

# Linux Fundamentals Part 2

## Task 1 Intro

### Read the above.

{% hint style="success" %}
No answer needed
{% endhint %}

### Deploy the machine attached to this task!

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 SSH - Intro

SSH is the act of remotely accessing a machine. SSH allows you to run commands interactively on the remote machine. This is done through the use of a program on the target machine, which allows the ssh client to interface with the target host.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 Putty and SSH

The syntax on how to use this command is `ssh <user>@<host>`.

### SSH into the server

* username: shiba2
* password: pinguftw

```
ssh shiba2@
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 4 \[Section 4: Linux Operators]: "&&"

&& means as you might expect "and". Meaning && allows you to execute a second command after the first one has executed successfully.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 5 \[Section 4: Linux Operators]: "&"

& is a background operator, meaning say you run a command that takes 10 seconds to run, normally you wouldn't be able to run commands during that period; however, with & that command will still execute and you'll be able to run other commands.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 6 \[Section 4: Linux Operators]: "$"

The $ is an unusually special operator, as it is used to denote environment variables.

`touch $USER`

Environment variables can also be set pretty easily, just running `export <varname>=<value>` will set that as an environment variable

### How would you set nootnoot equal to 1111&#x20;

{% hint style="success" %}
export nootnoot=1111
{% endhint %}

### What is the value of the home environment variable

```
echo $HOME
```

{% hint style="success" %}
/home/shiba2
{% endhint %}

## Task 7 \[Section 4: Linux Operators]: "|"

The pipe is unique because while operators like >> allow you to store the output of a command, the | operator allows you to take the output of a command and use it as input for a second command.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 8 \[Section 4: Linux Operators] - ";"

The ; operator works a lot like &&, however it does not require the first command to execute successfully.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 9 \[Section 4: Linux Operators]: ">"

\> is the operator for output redirection.

### How would you output twenty to a file called test

{% hint style="success" %}
echo twenty > test
{% endhint %}

## Task 10 \[Section 4: Linux Operators]: ">>"

\>> does mainly the same thing as >, with one key difference. >> appends the output of a command to a file, instead of erasing it.

### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 11 Binary - shiba2

What is shiba3's password

```
echo $USER
export test1234=shiba2
./shiba2 
```

![](<../.gitbook/assets/image (182).png>)

{% hint style="success" %}
happynootnoises
{% endhint %}

## Task 12 \[Section 5 - Advanced File Operations]: Intro



### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 13 \[Section 5 - Advanced File Operators]: A bit of background.



### Read the above

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 14 \[Section 5: Advanced File Operations]: chown

### How would you change the owner of file to paradox

{% hint style="success" %}
chown paradox file
{% endhint %}

### What about the owner and the group of file to paradox

{% hint style="success" %}
chown paradox:paradox file
{% endhint %}

### What flag allows you to operate on every file in the directory at once?

{% hint style="success" %}
\-R
{% endhint %}

## Task 15 \[Section 5: Advanced File Operations]: chmod

`chmod <permissions> <file>`

### What permissions mean the user can read the file, the group can read and write to the file, and no one else can read, write or execute the file?

{% hint style="success" %}
460
{% endhint %}

### What permissions mean the user can read, write, and execute the file, the group can read, write, and execute the file, and everyone else can read, write, and execute the file.

{% hint style="success" %}
777
{% endhint %}

## Task 16 \[Section 5: Advanced File Operations]: rm

rm  means remove

### What flag deletes every file in a directory

{% hint style="success" %}
\-r
{% endhint %}

### How do you suppress all warning prompts

{% hint style="success" %}
\-f
{% endhint %}

## Task 17 \[Section 5: Advanced File Operations]: mv

mv allows you to move files from one place to another.

### How would you move file to /tmp

{% hint style="success" %}
mv file /tmp
{% endhint %}

## Task 18 Linux Fundamentals 3

Join the Linux Fundamentals 3 room, and finish learning Linux: [https://tryhackme.com/room/linux3](https://tryhackme.com/room/linux3)

{% hint style="success" %}
No answer needed
{% endhint %}
