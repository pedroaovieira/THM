---
description: Web Exploitation
---

# Be careful with what you wish on a Christmas night

## Video

{% embed url="https://www.youtube.com/watch?v=cNYhpbUtkJw" %}

## Resources

[OWASP/CheatSheetSeries](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Input\_Validation\_Cheat\_Sheet.md)

Check out this awesome guide about XSS: [swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection)\
&#x20;Common payload list for you to try out: [payloadbox/xss-payload-list](https://github.com/payloadbox/xss-payload-list)\
&#x20;For more OWASP Zap guides, check out the following room: [Learn OWASP Zap](https://tryhackme.com/room/learnowaspzap)

## Challenge

### Deploy your AttackBox

![](<../.gitbook/assets/image (41).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### What vulnerability type was used to exploit the application?

![](<../.gitbook/assets/image (42).png>)

![](<../.gitbook/assets/image (43).png>)

{% hint style="success" %}
Stored cross-site scripting
{% endhint %}

### What query string can be abused to craft a reflected XSS?

![](<../.gitbook/assets/image (44).png>)

{% hint style="success" %}
q
{% endhint %}

### Launch the OWASP ZAP Application

![](<../.gitbook/assets/image (45).png>)

{% hint style="success" %}
No answer needed
{% endhint %}

### Run a ZAP (zaproxy) automated scan on the target. How many XSS alerts are in the scan?

![](<../.gitbook/assets/image (46).png>)

{% hint style="success" %}
2
{% endhint %}

### Explore the XSS alerts that ZAP has identified, are you able to make an alert appear on the "Make a wish" website?

![](<../.gitbook/assets/image (47).png>)

{% hint style="success" %}
No answer needed
{% endhint %}
