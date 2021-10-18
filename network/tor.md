---
description: https://tryhackme.com/room/torforbeginners
---

# TOR

## Task 1 Unit 1 - Tor

### Run apt-get install tor to install/update your Tor packages

{% hint style="success" %}
No answer needed
{% endhint %}

### Run service tor start to start the Tor service

{% hint style="success" %}
No answer needed
{% endhint %}

### Run service tor status to check Tor's availability

{% hint style="success" %}
No answer needed
{% endhint %}

### Run service tor stop to stop the Tor service

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 Unit 2 - Proxychains

Proxychains - a tool that forces any TCP connection made by any given application to follow through proxy like TOR or any other SOCKS4, SOCKS5 or HTTP(S) proxy.

Proxychains is widely used by pentesters during the reconnaissance stage (For example with nmap).

Let's start with running apt install proxychains to install/update proxychains tool

{% hint style="success" %}
No answer needed
{% endhint %}

Now it's time to configure proxychains to work properly

Run nano /etc/proxychains.conf to edit the settings. (Note: You can use any text editing tool instead of nano)

{% hint style="success" %}
No answer needed
{% endhint %}

We can now see, that most of the methods are under comment mark. You can read their description and decide on using one of them in the future. For this lesson let's uncomment dynamic\_chain and comment others (simply put '#' to the left). Additionally, it is useful to uncomment proxy\_dns in order to prevent DNS leak. Scroll through the document and see whenever you want to add some additional proxies at the bottom of the page (which is not required at this point).

Apply all the settings.

{% hint style="success" %}
No answer needed
{% endhint %}

Now let's check our settings.

Start the TOR service and run proxychains firefox. Usually, you are required to put 'proxychains' command before anything in order to force it to transfer data through Tor.

```
service tor start
proxychains firefox
```

{% hint style="success" %}
No answer needed
{% endhint %}

After the firefox has loaded, check if your IP address has changed with any website that provides such information. Also, try running a test on dnsleaktest.com and see if your DNS address changed too.

NOTE: All other web browser windows should be closed before opening firefox through proxychains!

![](<../.gitbook/assets/image (445).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 Unit 3 - Tor browser

### Finish the installation&#x20;

{% hint style="success" %}

{% endhint %}

### Launch the Tor Browser and set your privacy settings to Level 2 (Safer)

{% hint style="success" %}

{% endhint %}

### Access the website below and capture the flag by copying bitcoin address at the bottom of the page!

{% embed url="http://danielas3rtn54uwmofdo3x2bsdifr47huasnmbgqzfrec5ubupvtpid.onion/" %}

![](<../.gitbook/assets/image (446).png>)

{% hint style="success" %}
1K918TvvE4PMPzPuZT7zSDAQV4ZNUjHBm5
{% endhint %}
