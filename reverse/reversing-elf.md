# Reversing ELF

## Task 1 Crackme1

Let's start with a basic warmup, can you run the binary?

### What is the flag?

```
chmod +x crackme1
binwalk crackme1
./crackme1
```

![](<../.gitbook/assets/image (280).png>)

{% hint style="success" %}
flag{not\_that\_kind\_of\_elf}
{% endhint %}

## Task 2 Crackme2

Find the super-secret password! and use it to obtain the flag

### What is the super secret password ?

```
chmod +x crackme2
binwalk crackme2
strings crackme2| grep pass
./crackme2 super_secret_password
```

![](<../.gitbook/assets/image (281).png>)

{% hint style="success" %}
super\_secret\_password
{% endhint %}

### What is the flag ?

{% hint style="success" %}
flag{if\_i\_submit\_this\_flag\_then\_i\_will\_get\_points}
{% endhint %}

## Task 3 Crackme3

Use basic reverse engineering skills to obtain the flag

### What is the flag?

```
chmod +x crackme3
binwalk crackme3
strings crackme2| more
echo "ZjByX3kwdXJfNWVjMG5kX2xlNTVvbl91bmJhc2U2NF80bGxfN2gzXzdoMW5nNQ==" |base64 -d
```

![](<../.gitbook/assets/image (282).png>)

{% hint style="success" %}
f0r\_y0ur\_5ec0nd\_le55on\_unbase64\_4ll\_7h3\_7h1ng5
{% endhint %}

## Task 4 Crackme4

Analyze and find the password for the binary?

### What is the password ?

```
radare2 -d ./crackme4 password
[0x7faf1ff3c090]> aa
[0x7faf1ff3c090]> afl
[0x7faf1ff3c090]> pdf @sym.get_pwd
[0x7faf1ff3c090]> db 0x00400678
[0x7faf1ff3c090]> dc
[0x00400678]> pdf @sym.get_pwd
[0x00400678]> px @rbp-0x4
```

![](<../.gitbook/assets/image (283).png>)

{% hint style="success" %}
my\_m0r3\_secur3\_pwd
{% endhint %}

## Task 5 Crackme5

What will be the input of the file to get output Good game ?

### What is the input ?

```
chmod +x crackme5   
./crackme5
```

![](<../.gitbook/assets/image (284).png>)

```
radare2 -d ./crackme5
aaa
afl
pdf @main
db 0x0040082c
dc
px @rsi
```

![](<../.gitbook/assets/image (286).png>)

![](<../.gitbook/assets/image (285).png>)

{% hint style="success" %}
OfdlDSA|3tXb32\~X3tX@sX\`4tXtz
{% endhint %}

## Task 6 Crackme6

Analyze the binary for the easy password

### What is the password ?

```
radare2 -d ./crackme6
aaa
afl

pdf @main
pdf @sym.compare_pwd
pdf @sym.my_secure_test

db 0x004006e1

0x31
0x33
0x33
0x37
0x5f
0x70
0x77
0x64

```

![](<../.gitbook/assets/image (287).png>)

![](<../.gitbook/assets/image (288).png>)

![](<../.gitbook/assets/image (292).png>)

{% hint style="success" %}
1337\_pwd
{% endhint %}

## Task 7 Crackme7

Analyze the binary to get the flag

### What is the flag ?

```
Ghidra
```

![](<../.gitbook/assets/image (289).png>)

```
python
print(int('0x7a69',16))
```

![](<../.gitbook/assets/image (291).png>)

![](<../.gitbook/assets/image (290).png>)

{% hint style="success" %}
31337
{% endhint %}

## Task 8 Crackme8

Analyze the binary and obtain the flag

### What is the flag ?

```
python
print(int('-0x35010ff3',16))
-889262067
```

![](<../.gitbook/assets/image (293).png>)

{% hint style="success" %}
flag{at\_least\_this\_cafe\_wont\_leak\_your\_credit\_card\_numbers}
{% endhint %}
