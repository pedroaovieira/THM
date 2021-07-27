---
description: Networking - NMAP
---

# What's Under the Christmas Tree?

## Video

{% embed url="https://www.youtube.com/watch?v=StmtQKoFiWg" %}

## Resources

[Penetration Testing Execution Standard](http://www.pentest-standard.org/index.php/Main_Page) \(PTES\)

Connect Scan - `nmap -sT <ip>`

SYN Scan - `nmap -sS <ip>`

[NSE Scripts](https://nmap.org/nsedoc/scripts/)

`nmap --script ftp-proftpd-backdoor -p 21 <ip_address>`

| Flag | Description |
| :--- | :--- |
| -A | Scan the host to identify services running by matching against Nmap's database with OS detection |
| -O | Scan the host to retrieve and perform OS detection |
| -p | Scan a specific port number on the host. A range of ports can also be provided \(i.e. 10-100\) by using the first and last value of the range |
| -p- | Scan all ports \(0-65535\) on the host |
| -sV | Scan the host using TCP and perform version fingerprinting |

## Challenge

### When was Snort created?

> https://en.wikipedia.org/wiki/Snort\_\(software\)

{% hint style="success" %}
1998
{% endhint %}

### Using Nmap on 10.10.127.159 , what are the port numbers of the three services running? \(Please provide your answer in ascending order/lowest -&gt; highest, separated by a comma\)

{% hint style="success" %}
80,2222,3389
{% endhint %}

### Run a scan and provide the **`-Pn`** flag to ignore ICMP being used to determine if the host is up

{% hint style="success" %}
No answer needed
{% endhint %}

### Experiment with different scan settings such as **`-A`** and **`-sV`** whilst comparing the outputs given.

{% hint style="success" %}
No answer needed
{% endhint %}

### Use Nmap to determine the name of the Linux distribution that is running, what is reported as the most likely distribution to be running?

![](../.gitbook/assets/image%20%2836%29.png)

{% hint style="success" %}
Ubuntu
{% endhint %}

### Use Nmap's Network Scripting Engine \(NSE\) to retrieve the "HTTP-TITLE" of the webserver. Based on the value returned, what do we think this website might be used for?

![](../.gitbook/assets/image%20%2835%29.png)

{% hint style="success" %}
Blog
{% endhint %}

### Now use different scripts against the remaining services to discover any further information about them

{% hint style="success" %}
No answer needed
{% endhint %}

