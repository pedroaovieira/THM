---
description: Forensics
---

# Time for some ELForensics

## Video

{% embed url="https://www.youtube.com/watch?v=tb3Bfy9nBhM" %}

## Resources

With PowerShell, we can obtain the hash of a file by running the following command: `Get-FileHash -Algorithm MD5 file.txt`

Another tool you can use to inspect within a binary file (.exe) is `Strings.exe`

The command to run for the Strings tool to scan the mysterious executable: `c:\Tools\strings64.exe -accepteula file.exe`

The command to view ADS using Powershell: `Get-Item -Path file.exe -Stream *`

The command to run to launch the hidden executable hiding within ADS: `wmic process call create $(Resolve-Path file.exe:streamname)`

## Challenge

### Read the contents of the text file within the Documents folder. What is the file hash for db.exe?

```
PS C:\Users\littlehelper> cd .\Documents\
PS C:\Users\littlehelper\Documents> dir
PS C:\Users\littlehelper\Documents> cat '.\db file hash.txt'
```

{% hint style="success" %}
596690FFC54AB6101932856E6A78E3A1
{% endhint %}

### What is the file hash of the mysterious executable within the Documents folder?

```
PS C:\Users\littlehelper\Documents> Get-FileHash -Algorithm MD5 deebee.exe
```

![](<../.gitbook/assets/image (275).png>)

{% hint style="success" %}
5F037501FB542AD2D9B06EB12AED09F0
{% endhint %}

### Using Strings find the hidden flag within the executable?

```
PS C:\Users\littlehelper\Documents> c:\Tools\strings64.exe -accepteula .\deebee.exe
```

![](<../.gitbook/assets/image (276).png>)

{% hint style="success" %}
THM{f6187e6cbeb1214139ef313e108cb6f9}
{% endhint %}

### What is the flag that is displayed when you run the database connector file?

```
Get-Item -Path file.exe -Stream *
```

![](<../.gitbook/assets/image (277).png>)

```
PS C:\Users\littlehelper\Documents> wmic process call create $(Resolve-Path .\deebee.exe:hidedb)
```

![](<../.gitbook/assets/image (278).png>)

{% hint style="success" %}
THM{088731ddc7b9fdeccaed982b07c297c}
{% endhint %}
