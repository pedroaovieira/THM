---
description: Forensics
---

# The Grinch strikes again!

## Video

{% embed url="https://www.youtube.com/watch?v=rY1qsQIOl8I" %}

## Resources

The Volume Shadow Copy Service \(VSS\) coordinates the actions that are required to create a consistent shadow copy \(also known as a snapshot or a point-in-time copy\) of the data that is to be backed up.

The command to interact with VSS is `vssadmin`. Running the command alone will display brief information on how to run the utility with additional commands. Two commands of particular interest are `List Volumes` and `List Shadows`.

## Challenge

Decrypt the fake 'bitcoin address' within the ransom note. What is the plain text value?

![](../.gitbook/assets/image%20%28357%29.png)

![](../.gitbook/assets/image%20%28349%29.png)

{% hint style="success" %}
nomorebestfestivalcompany
{% endhint %}

At times ransomware changes the file extensions of the encrypted files. What is the file extension for each of the encrypted files?

![](../.gitbook/assets/image%20%28358%29.png)

![](../.gitbook/assets/image%20%28352%29.png)

{% hint style="success" %}
.grinch
{% endhint %}

What is the name of the suspicious scheduled task?

![](../.gitbook/assets/image%20%28355%29.png)

{% hint style="success" %}
opidsfsdf
{% endhint %}

Inspect the properties of the scheduled task. What is the location of the executable that is run at login?

![](../.gitbook/assets/image%20%28356%29.png)

{% hint style="success" %}
C:\Users\Administrator\Desktop\opidsfsdf.exe
{% endhint %}

There is another scheduled task that is related to VSS. What is the ShadowCopyVolume ID?

![](../.gitbook/assets/image%20%28354%29.png)

{% hint style="success" %}
7a9eea15-0000-0000-0000-010000000000
{% endhint %}

Assign the hidden partition a letter. What is the name of the hidden folder?

![](../.gitbook/assets/image%20%28350%29.png)

![](../.gitbook/assets/image%20%28353%29.png)

{% hint style="success" %}
confidential
{% endhint %}

Right-click and inspect the properties for the hidden folder. Use the 'Previous Versions' tab to restore the encrypted file that is within this hidden folder to the previous version. What is the password within the file?

![](../.gitbook/assets/image%20%28351%29.png)

{% hint style="success" %}
m33pa55w0rdIZseecure!
{% endhint %}

