---
description: Web Exploitation - Burp Suite
---

# Christmas Chaos

## Video

{% embed url="https://www.youtube.com/watch?v=cQq6xPCZFjg&" %}

## Resources

[SecLists](https://github.com/danielmiessler/SecLists/) is a collection of common lists including usernames, passwords, URLs and much more.

A password list known as "**rockyou.txt**" is commonly used in security challenges, and should definitely be a part of your security toolkit.

## Challenge

### Deploy your AttackBox

{% hint style="success" %}
No answer needed
{% endhint %}

![](<../.gitbook/assets/image (16).png>)

Use Burp Suite as proxy and intercept the request in Burp Suite.

![](<../.gitbook/assets/image (19).png>)

**`Send to Intruder`** --> **`Positions`**

Select **`Attack Type`** **`Cluster Bomb`**

Use BurpSuite to brute force the login form. Use the following lists for the default credentials:&#x20;

| Username | Password |
| -------- | -------- |
| root     | root     |
| admin    | password |
| user     | 12345    |

**`Payloads`**

![](<../.gitbook/assets/image (20).png>)

![](<../.gitbook/assets/image (21).png>)

`Start attack`

![](<../.gitbook/assets/image (22).png>)

Looking at the results, the pair **`admin`** **`12345`** as a different size length result.

![](<../.gitbook/assets/image (23).png>)

Use the correct credentials to log in to the Santa Sleigh Tracker app. Don't forget to turn off Foxyproxy once BurpSuite has finished the attack!

![](<../.gitbook/assets/image (24).png>)

### What is the flag?

{% hint style="success" %}
THM{885ffab980e049847516f9d8fe99ad1a}
{% endhint %}
