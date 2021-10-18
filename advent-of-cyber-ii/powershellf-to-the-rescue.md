---
description: Powershell
---

# PowershELlF to the rescue

## Video

{% embed url="https://youtu.be/LrdT2hUM6mw" %}

## Resources

To list the contents of the current directory we are in, we can use the `Get-ChildItem` cmdlet.  There are various other options we can use with this cmdlet to enhance its capabilities further.

* `-Path` Specifies a path to one or more locations. Wildcards are accepted.
* `-File / -Directory` To get a list of files, use the File parameter. To get a list of directories, use the Directory parameter. You can use the Recurse parameter with File and/or Directory parameters.
* `-Filter` Specifies a filter to qualify the Path parameter.
* `-Recurse` Gets the items in the specified locations and in all child items of the locations.
* `-Hidden` To get only hidden items, use the Hidden parameter.
* `-ErrorAction SilentlyContinue` Specifies what action to take if the command encounters an error.

For example, if you want to view all of the hidden files in the current directory you are in, you can issue the following command: `Get-ChildItem -File -Hidden -ErrorAction SilentlyContinue`

Another useful cmdlet is `Get-Content`. This will allow you to read the contents of a file.

You can run this command as follows: `Get-Content -Path file.txt`

You can run numerous operations with the `Get-Content` cmdlet to give you more information about the particular file you are inspecting. Such as how many words are in the file and the exact positions for a particular string within a file.

To get the number of words contained within a file, you can use the `Get-Content` cmdlet and pipe the results to the `Measure-Object` cmdlet.

You run this command as follows: `Get-Content -Path file.txt | Measure-Object -Word`

To get the exact position of a string within the file, you can use the following command:  `(Get-Content -Path file.txt)[index]`

The index is the numerical value that is the location of the string within the file. Since indexes start at zero, you typically need to subtract one from the original value to extract the string at the correct position. This is not necessary for this exercise.

To change directories, you can use the `Set-Location` cmdlet.

For example, `Set-Location -Path c:\users\administrator\desktop ` will change your location to the Administrator's desktop.

The last cmdlet that is needed to solve this room is `Select-String`. This cmdlet will search a particular file for a pattern you define within the command to run.

An example execution of this command is: `Select-String -Path 'c:\users\administrator\desktop' -Pattern '*.pdf'`

Note: You can always use the `Get-Help` cmdlet to obtain more information about a specific cmdlet. For example, `Get-Help Select-String`

## Challenge

`ssh -l mceager 10.10.114.147`

`r0ckStar!`

![](<../.gitbook/assets/image (196).png>)

```bash
powershell
```

![](<../.gitbook/assets/image (197).png>)

### Search for the first hidden elf file within the Documents folder. Read the contents of this file. What does Elf 1 want?

```bash
Set-Location .\Documents\           or        cd .\Documents\
cd .\Documents\                     or        ls -Hidden
Get-Content -Path .\e1fone.txt      or        cat .\e1fone.txt
```

![](<../.gitbook/assets/image (198).png>)

{% hint style="success" %}
2 front teeth
{% endhint %}

### Search on the desktop for a hidden folder that contains the file for Elf 2. Read the contents of this file. What is the name of that movie that Elf 2 wants?

```bash
cd ..
cd .\Desktop\
ls -Directory -Hidden
cd .\elf2wo
Get-Content -Path .\e70smsW10Y4k.txt        or         cat .\e70smsW10Y4k.txt
```

![](<../.gitbook/assets/image (199).png>)

{% hint style="success" %}
Scrooged
{% endhint %}

### Search the Windows directory for a hidden folder that contains files for Elf 3. What is the name of the hidden folder? (This command will take a while)

```bash
gci C:\Windows\ -Recurse -Directory -Hidden -Filter "*3*" -ErrorAction SilentlyContinue
cd c:\Windows\System32\3lfthr3e
ls -Directory -Hidden

```

![](<../.gitbook/assets/image (200).png>)

{% hint style="success" %}
3lfthr3e
{% endhint %}

### How many words does the first file contain?

```bash
cd c:\Windows\System32\3lfthr3e
ls -Hidden
Get-Content -Path 1.txt | Measure-Object -Word        or        (gc .\1.txt).length
```

![](<../.gitbook/assets/image (201).png>)

{% hint style="success" %}
9999
{% endhint %}

### What 2 words are at index 551 and 6991 in the first file?

```bash
(Get-Content -Path 1.txt)[551]         or        (gc .\1.txt)[551]
(Get-Content -Path 1.txt)[6991]        or        (gc .\1.txt)[6991]
```

![](<../.gitbook/assets/image (202).png>)

{% hint style="success" %}
Red Ryder
{% endhint %}

### This is only half the answer. Search in the 2nd file for the phrase from the previous question to get the full answer. What does Elf 3 want? (use spaces when submitting the answer)

```bash
Select-String -Path .\2.txt -Pattern 'RedRyder'
```

![](<../.gitbook/assets/image (195).png>)

{% hint style="success" %}
Red Ryder bb gun
{% endhint %}
