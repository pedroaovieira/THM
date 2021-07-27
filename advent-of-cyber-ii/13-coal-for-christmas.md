---
description: Special
---

# Coal for Christmas

## Video

{% embed url="https://www.youtube.com/watch?v=LSRhro8x2mQ" %}

## Resources

There is a great list of commands you can run for enumeration here: [https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)

## Challenge

### Hi Santa, hop in your sleigh and deploy this machine!

{% hint style="success" %}
No answer needed
{% endhint %}

The Christmas GPS now says this house is at the address 10.10.159.83. Scan this machine with a port-scanning tool of your choice.

**Port Scanning**

We will begin by scanning the machine. If you are working from the TryHackMe "Attackbox" or from a Kali Linux instance \(or honestly, any Linux distribution where you have this installed\), you can use **nmap** with syntax like so:

```text
nmap 10.10.159.83
```

![](../.gitbook/assets/image%20%2889%29.png)

{% hint style="success" %}
No answer needed
{% endhint %}

### What old, deprecated protocol and service is running?

{% hint style="success" %}
Telnet
{% endhint %}

**Initial Access**

Connect to this service to see if you can make use of it. You can connect to the service with the standard command-line client, named after the name of the service, or **netcat** with syntax like this:

```text
telnet 10.10.159.83 23
```

![](../.gitbook/assets/image%20%2886%29.png)

### What credential was left for you? 

{% hint style="success" %}
clauschristmas
{% endhint %}

**Enumeration**

Looks like you can slide right down the chimney! Log in and take a look around, enumerate a bit. You can view files and folders in the current directory with **ls**, change directories with **cd** and view the contents of files with **cat**.

![](../.gitbook/assets/image%20%2892%29.png)

```text
./christmas.sh
```

![](../.gitbook/assets/image%20%2888%29.png)

Often to enumerate you want to look at pertinent system information, like the version of the operating system or other release information. You can view some information with commands like this:

```text
cat /etc/*release
```

```text
uname -a 
```

```text
cat /etc/issue 
```

There is a great list of commands you can run for enumeration here: [https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)

### What distribution of Linux and version number is this server running?

{% hint style="success" %}
Ubuntu 12.04
{% endhint %}

This is a very _old_ version of Linux! This may be vulnerable to some kernel exploits, that we could use to escalate our privileges.

Take a look at the cookies and milk that the server owners left for you. You can do this with the **cat** command as mentioned earlier.

cat cookies\_and\_milk.txt

```text
cat cookies_and_milk.txt | more
```

![](../.gitbook/assets/image%20%2894%29.png)

### Who got here first?

{% hint style="success" %}
grinch
{% endhint %}

The perpetrator took half of the cookies and milk! Weirdly enough, that file looks like C code...

That C source code is a portion of a kernel exploit called **DirtyCow**. Dirty COW \(CVE-2016-5195\) is a privilege escalation vulnerability in the Linux Kernel, taking advantage of a race condition that was found in the way the Linux kernel's memory subsystem handled the copy-on-write \(COW\) breakage of private read-only memory mappings. An unprivileged local user could use this flaw to gain write access to otherwise read-only memory mappings and thus increase their privileges on the system.

You can learn more about the DirtyCow exploit online here: [https://dirtycow.ninja/](https://dirtycow.ninja/)

This **cookies\_and\_milk.txt** file looks like a modified rendition of a DirtyCow exploit, usually written in C. Find a copy of that original file online, and get it on the target box. You can do this with some simple file transfer methods like netcat, or spinning up a quick Python HTTP server... or you can simply copy-and-paste it into a text editor on the box!

{% hint style="success" %}
No answer needed
{% endhint %}

{% embed url="https://github.com/FireFart/dirtycow/blob/master/dirty.c" %}

You can compile the C source code on the target with **gcc**. You might need to supply specific parameters or arguments to include different libraries, but thankfully, the DirtyCow source code will explain what syntax to use.

### What is the verbatim syntax you can use to compile, taken from the real C source code comments?

![](../.gitbook/assets/image%20%2891%29.png)

{% hint style="success" %}
gcc -pthread dirty.c -o dirty -lcrypt
{% endhint %}

**Privilege Escalation**

Run the commands to compile the exploit, and run it.

![](../.gitbook/assets/image%20%2887%29.png)

### What "new" username was created, with the default operations of the real C source code? 

{% hint style="success" %}
firefart
{% endhint %}

### Switch your user into that new user account, and hop over to the /root directory to own this server!

You can switch user accounts like so:

su &lt;user\_to\_change\_to&gt;

{% hint style="success" %}
No answer needed
{% endhint %}

Uh oh, looks like that perpetrator left a message! Follow his instructions to prove you really did leave Coal for Christmas!

After you leave behind the coal, you can run tree \| md5sum

### What is the MD5 hash output?

```text
su firefart
password

```

![](../.gitbook/assets/image%20%2885%29.png)

```text
touch coal
tree |md5
```

![](../.gitbook/assets/image%20%2890%29.png)

{% hint style="success" %}
8b16f00dd3b51efadb02c1df7f8427cc
{% endhint %}

