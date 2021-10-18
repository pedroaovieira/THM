---
description: https://tryhackme.com/room/furthernmap
---

# Nmap

## Task 1 Deploy

Deploy the attached VM

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 Introduction

Every computer has a total of 65535 available ports;

### What networking constructs are used to direct traffic to the right application on a server?

{% hint style="success" %}
Ports
{% endhint %}

### How many of these are available on any network-enabled computer?

{% hint style="success" %}
65535
{% endhint %}

### **\[Research]** How many of these are considered "well-known"? (These are the "standard" numbers mentioned in the task)

{% hint style="success" %}
1024
{% endhint %}

## Task 3 Nmap Switches

### What is the first switch listed in the help menu for a 'Syn Scan' (more on this later!)?

{% hint style="success" %}
\-sS
{% endhint %}

### Which switch would you use for a "UDP scan"?

{% hint style="success" %}
\-sU
{% endhint %}

### If you wanted to detect which operating system the target is running on, which switch would you use?

{% hint style="success" %}
\-O
{% endhint %}

### Nmap provides a switch to detect the version of the services running on the target. What is this switch?

{% hint style="success" %}
\-sV
{% endhint %}

### The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?

{% hint style="success" %}
\-v
{% endhint %}

### Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two?  (**Note**: it's highly advisable to always use _at least_ this option)

{% hint style="success" %}
\-vv
{% endhint %}

### We should always save the output of our scans -- this means that we only need to run the scan once (reducing network traffic and thus chance of detection), and gives us a reference to use when writing reports for clients.

### What switch would you use to save the nmap results in three major formats?

{% hint style="success" %}
\-oA
{% endhint %}

### What switch would you use to save the nmap results in a "normal" format?

{% hint style="success" %}
\-oN
{% endhint %}

### A very useful output format: how would you save results in a "grepable" format?

{% hint style="success" %}
\-oG
{% endhint %}

### Sometimes the results we're getting just aren't enough. If we don't care about how loud we are, we can enable "aggressive" mode. This is a shorthand switch that activates service detection, operating system detection, a traceroute and common script scanning.

### How would you activate this setting?

{% hint style="success" %}
\-A
{% endhint %}

### Nmap offers five levels of "timing" template. These are essentially used to increase the speed your scan runs at. Be careful though: higher speeds are noisier, and can incur errors!

### How would you set the timing template to level 5?

{% hint style="success" %}
\-T5
{% endhint %}

### We can also choose which port(s) to scan.

### How would you tell nmap to only scan port 80?

{% hint style="success" %}
\-p 80
{% endhint %}

### How would you tell nmap to scan ports 1000-1500?

{% hint style="success" %}
\-p 1000-1500
{% endhint %}

### A very useful option that should not be ignored:

### How would you tell nmap to scan _all_ ports?

{% hint style="success" %}
\-p-
{% endhint %}

### How would you activate a script from the nmap scripting library (lots more on this later!)?

{% hint style="success" %}
\--script
{% endhint %}

### How would you activate all of the scripts in the "vuln" category?

{% hint style="success" %}
\--script=vuln
{% endhint %}

## Task 4 \[Scan Types] Overview

When port scanning with Nmap, there are three basic scan types. These are:

* TCP Connect Scans (`-sT`)
* SYN "Half-open" Scans (`-sS`)
* UDP Scans (`-sU`)

Additionally there are several less common port scan types, some of which we will also cover (albeit in less detail). These are:

* TCP Null Scans (`-sN`)
* TCP FIN Scans (`-sF`)
* TCP Xmas Scans (`-sX`)

Read the Scan Types Introduction.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 5 \[Scan Types] TCP Connect Scans

To understand TCP Connect scans (`-sT`), it's important that you're comfortable with the _TCP three-way handshake_.

![](<../.gitbook/assets/image (244).png>)

Many firewalls are configured to simply **drop** incoming packets. For example, in IPtables for Linux, a simple version of the command would be as follows:

`iptables -I INPUT -p tcp --dport <port> -j REJECT --reject-with tcp-reset`

### Which RFC defines the appropriate behaviour for the TCP protocol?

{% hint style="success" %}
RFC 793
{% endhint %}

### If a port is closed, which flag should the server send back to indicate this?

{% hint style="success" %}
RST
{% endhint %}

## Task 6 \[Scan Types] SYN Scans

As with TCP scans, SYN scans (`-sS`) are used to scan the TCP port-range of a target or targets; however, the two scan types work slightly differently. SYN scans are sometimes referred to as "Half-open" scans, or "Stealth" scans.

![](<../.gitbook/assets/image (245).png>)

This has a variety of advantages for us as hackers:

* It can be used to bypass older Intrusion Detection systems as they are looking out for a full three way handshake. This is often no longer the case with modern IDS solutions; it is for this reason that SYN scans are still frequently referred to as "stealth" scans.
* SYN scans are often not logged by applications listening on open ports, as standard practice is to log a connection once it's been fully established. Again, this plays into the idea of SYN scans being stealthy.
* Without having to bother about completing (and disconnecting from) a three-way handshake for every port, SYN scans are significantly faster than a standard TCP Connect scan.

There are, however, a couple of disadvantages to SYN scans, namely:

* They require sudo permissions\[1] in order to work correctly in Linux. This is because SYN scans require the ability to create raw packets (as opposed to the full TCP handshake), which is a privilege only the root user has by default.
* Unstable services are sometimes brought down by SYN scans, which could prove problematic if a client has provided a production environment for the test.

### &#x20;There are two other names for a SYN scan, what are they?

{% hint style="success" %}
Half-Open, Stealth
{% endhint %}

### Can Nmap use a SYN scan without Sudo permissions (Y/N)?

{% hint style="success" %}
N
{% endhint %}

## Task 7 \[Scan Types] UDP Scans

Unlike TCP, UDP connections are stateless. This means that, rather than initiating a connection with a back-and-forth "handshake", UDP connections rely on sending packets to a target port and essentially hoping that they make it. This makes UDP superb for connections which rely on speed over quality (e.g. video sharing), but the lack of acknowledgement makes UDP significantly more difficult (and much slower) to scan. The switch for an Nmap UDP scan is (`-sU`)

When a packet is sent to an open UDP port, there should be no response. When this happens, Nmap refers to the port as being `open|filtered`. In other words, it suspects that the port is open, but it could be firewalled. If it gets a UDP response (which is very unusual), then the port is marked as open. More commonly there is no response, in which case the request is sent a second time as a double-check. If there is still no response then the port is marked open|filtered and Nmap moves on.

For example, scanning with  `nmap -sU --top-ports 20 <target>`. Will scan the top 20 most commonly used UDP ports, resulting in a much more acceptable scan time.

### If a UDP port doesn't respond to an Nmap scan, what will it be marked as?

{% hint style="success" %}
open|filtered
{% endhint %}

### When a UDP port is closed, by convention the target should send back a "port unreachable" message. Which protocol would it use to do so?

{% hint style="success" %}
ICMP
{% endhint %}

## Task 8 \[Scan Types] NULL, FIN and Xmas

NULL, FIN and Xmas TCP port scans are less commonly used than any of the others we've covered already, so we will not go into a huge amount of depth here. All three are interlinked and are used primarily as they tend to be even stealthier, relatively speaking, than a SYN "stealth" scan. Beginning with NULL scans:

* As the name suggests, NULL scans (`-sN`) are when the TCP request is sent with no flags set at all. As per the RFC, the target host should respond with a RST if the port is closed.\
  ![](https://i.imgur.com/ABCxAwf.png)
* FIN scans (`-sF`) work in an almost identical fashion; however, instead of sending a completely empty packet, a request is sent with the FIN flag (usually used to gracefully close an active connection). Once again, Nmap expects a RST if the port is closed.\
  ![](https://i.imgur.com/gIzKbEk.png)
* As with the other two scans in this class, Xmas scans (`-sX`) send a malformed TCP packet and expects a RST response for closed ports. It's referred to as an xmas scan as the flags that it sets (PSH, URG and FIN) give it the appearance of a blinking christmas tree when viewed as a packet capture in Wireshark.\
  ![](https://i.imgur.com/gKVkGug.png)

The expected response for open ports with these scans is also identical, and is very similar to that of a UDP scan.

&#x20;Which of the three shown scan types uses the URG flag?

{% hint style="success" %}
xmas
{% endhint %}

Why are NULL, FIN and Xmas scans generally used?

{% hint style="success" %}
Firewall Evasion
{% endhint %}

Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?

{% hint style="success" %}
Microsoft Windows
{% endhint %}

## Task 9 \[Scan Types] ICMP Network Scanning

To perform a ping sweep, we use the `-sn` switch in conjunction with IP ranges which can be specified with either a hypen (`-`) or CIDR notation. i.e. we could scan the `192.168.0.x` network using:

* `nmap -sn 192.168.0.1-254`

or

* `nmap -sn 192.168.0.0/24`

The `-sn` switch tells Nmap not to scan any ports -- forcing it to rely purely on ICMP packets (or ARP requests on a local network) to identify targets.

### How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)

{% hint style="success" %}
nmap -sn 172.16.0.0/16
{% endhint %}

## Task 10 \[NSE Scripts] Overview

Some useful categories include:

* `safe`:- Won't affect the target
* `intrusive`:- Not safe: likely to affect the target\

* `vuln`:- Scan for vulnerabilities
* `exploit`:- Attempt to exploit a vulnerability
* `auth`:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
* `brute`:- Attempt to bruteforce credentials for running services
* `discovery`:- Attempt to query running services for further information about the network (e.g. query an SNMP server).

A more exhaustive list can be found [here](https://nmap.org/book/nse-usage.html).

### &#x20;What language are NSE scripts written in?

{% hint style="success" %}
Lua
{% endhint %}

### Which category of scripts would be a very bad idea to run in a production environment?

{% hint style="success" %}
intrusive
{% endhint %}

## Task 11 \[NSE Scripts] Working with the NSE

To run a specific script, we would use `--script=<script-name>` , e.g. `--script=http-fileupload-exploiter`.

Multiple scripts can be run simultaneously in this fashion by separating them by a comma. For example: `--script=smb-enum-users,smb-enum-shares`.

Nmap scripts come with built-in help menus, which can be accessed using `nmap --script-help <script-name>`.

### What optional argument can the `ftp-anon.nse` script take?

{% hint style="success" %}
maxlist
{% endhint %}

## Task 12 \[NSE Scripts] Searching for Scripts

Nmap stores its scripts on Linux at `/usr/share/nmap/scripts`

`grep "ftp" /usr/share/nmap/scripts/script.db`

`ls -l /usr/share/nmap/scripts/*ftp*`

`grep "safe" /usr/share/nmap/scripts/script.db`

### Search for "smb" scripts in the `/usr/share/nmap/scripts/` directory using either of the demonstrated methods. What is the filename of the script which determines the underlying OS of the SMB server?

{% hint style="success" %}
smb-os-discovery.nse
{% endhint %}

### Read through this script. What does it depend on?

{% hint style="success" %}
smb-brute
{% endhint %}

## Task 13 Firewall Evasion

Nmap provides an option for this: `-Pn`, which tells Nmap to not bother pinging the host before scanning it. This means that Nmap will always treat the target host(s) as being alive, effectively bypassing the ICMP block;

The following switches are of particular note:

* `-f`:- Used to fragment the packets (i.e. split them into smaller pieces) making it less likely that the packets will be detected by a firewall or IDS.
* An alternative to `-f`, but providing more control over the size of the packets: `--mtu <number>`, accepts a maximum transmission unit size to use for the packets sent. This must be a multiple of 8.
* `--scan-delay <time>ms`:- used to add a delay between packets sent. This is very useful if the network is unstable, but also for evading any time-based firewall/IDS triggers which may be in place.
* `--badsum`:- this is used to generate in invalid checksum for packets. Any real TCP/IP stack would drop this packet, however, firewalls may potentially respond automatically, without bothering to check the checksum of the packet. As such, this switch can be used to determine the presence of a firewall/IDS.

### &#x20;Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the `-Pn` switch?

{% hint style="success" %}
ICMP
{% endhint %}

### **\[Research]** Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?

{% hint style="success" %}
\--data-length
{% endhint %}

## Task 14 Practical

### Does the target (`MACHINE_IP`)respond to ICMP (ping) requests (Y/N)?

```
nmap -PE 10.10.19.105
```

{% hint style="success" %}
N
{% endhint %}

### Perform an Xmas scan on the first 999 ports of the target -- how many ports are shown to be open or filtered?

```
sudo nmap -sX -p 1-999 10.10.19.105 -Pn
```

![](<../.gitbook/assets/image (248).png>)

{% hint style="success" %}
999
{% endhint %}

### There is a reason given for this -- what is it?

**Note:** The answer will be in your scan results. Think carefully about which switches to use -- and read the hint before asking for help!

{% hint style="success" %}
No Response
{% endhint %}

### Perform a TCP SYN scan on the first 5000 ports of the target -- how many ports are shown to be open?

```
nmap -sS -p 1-5000 --open -Pn 10.10.19.105
```

![](<../.gitbook/assets/image (247).png>)

{% hint style="success" %}
5
{% endhint %}

### Open Wireshark (see [Cryillic's](https://tryhackme.com/p/Cryillic) [Wireshark Room](https://tryhackme.com/room/wireshark) for instructions) and perform a TCP Connect scan against port 80 on the target, monitoring the results. Make sure you understand what's going on.

{% hint style="success" %}
No answer needed
{% endhint %}

### Deploy the `ftp-anon` script against the box. Can Nmap login successfully to the FTP server on port 21? (Y/N)

```
nmap --script ftp-anon -p 21 10.10.19.105 -Pn
```

![](<../.gitbook/assets/image (249).png>)

{% hint style="success" %}
Y
{% endhint %}

## Task 15 Conclusion

### Read the conclusion.

{% hint style="success" %}
No answer needed
{% endhint %}
