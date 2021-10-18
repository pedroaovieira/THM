---
description: https://tryhackme.com/room/picklerick
---

# Pickle Rick

## INIT

```
export pickle=10.10.173.224
ping $pickle

echo "10.10.173.224 pickle.thm" >> /etc/hosts
```

## NMAP

```
nmap -v -sC -sV -O -T5 -p1-65535 pickle.thm
```

![](<../.gitbook/assets/image (399).png>)

## HTTP

![](<../.gitbook/assets/image (400).png>)

![](<../.gitbook/assets/image (401).png>)

{% hint style="info" %}
Username: R1ckRul3s
{% endhint %}

![](<../.gitbook/assets/image (403).png>)

{% hint style="info" %}
Wubbalubbadubdub
{% endhint %}

## GOBUSTER

```
gobuster dir -u pickle.thm -w /usr/share/wordlists/dirb/common.txt -q -t 15 -x php,html,txt
```

![](<../.gitbook/assets/image (405).png>)

## Login

{% hint style="info" %}
Username: R1ckRul3s

Password: Wubbalubbadubdub
{% endhint %}

![](<../.gitbook/assets/image (404).png>)

![](<../.gitbook/assets/image (412).png>)

## What is the first ingredient Rick needs?

![](<../.gitbook/assets/image (406).png>)

![](<../.gitbook/assets/image (408).png>)

{% hint style="success" %}
mr. meeseek hair
{% endhint %}

## Whats the second ingredient Rick needs?

![](<../.gitbook/assets/image (409).png>)

![](<../.gitbook/assets/image (410).png>)

{% hint style="success" %}
1 jerry tear
{% endhint %}

## Whats the final ingredient Rick needs?

![](<../.gitbook/assets/image (411).png>)

![](<../.gitbook/assets/image (413).png>)

![](<../.gitbook/assets/image (414).png>)

{% hint style="success" %}
fleeb juice
{% endhint %}
