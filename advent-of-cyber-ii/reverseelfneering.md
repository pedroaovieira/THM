---
description: Reverse Engineering
---

# ReverseELFneering

## Video

{% embed url="https://www.youtube.com/watch?v=5X5SHprLHts" %}

## Resources

Start radare2: `r2 -d ./file1`

Analyze the program: `aa`  It analyses all symbols and entry points in the executable

For general help, we can run: `?` or if we wish to understand more about a specific feature, we could provide `a?`

To find a list of the functions run: `afl`

Let’s examine the assembly code at main by running the command `pdf @main` Where `pdf` means print disassembly function.

| Initial Data Type |  Suffix | Size (bytes) |
| :---------------: | :-----: | :----------: |
|        Byte       |    b    |       1      |
|        Word       |    w    |       2      |
|    Double Word    |    l    |       4      |
|        Quad       |    q    |       8      |
|  Single Precision |    s    |       4      |
|  Double Precision |    l    |       8      |

When dealing with memory manipulation using registers, there are other cases to be considered:

* (Rb, Ri) = MemoryLocation\[Rb + Ri]
* D(Rb, Ri) = MemoryLocation\[Rb + Ri + D]
* (Rb, Ri, S) = MemoryLocation(Rb + S \* Ri]
* D(Rb, Ri, S) = MemoryLocation\[Rb + S \* Ri + D]

Instructions:

* **leaq** source, destination: this instruction sets destination to the address denoted by the expression in source
* **addq** source, destination: destination = destination + source&#x20;
* **subq** source, destination: destination = destination - source&#x20;
* **imulq** source, destination: destination = destination \* source&#x20;
* **salq** source, destination: destination = destination << source where << is the left bit shifting operator
* **sarq** source, destination: destination = destination >> source where >> is the right bit shifting operator
* **xorq** source, destination: destination = destination XOR source andq source, destination: destination = destination & source
* **orq** source, destination: destination = destination | source

A breakpoint specifies where the program should stop executing. `db @memory-address` and the parameter must be the memory address.

Run the program using `dc`

To view the contents of the local\_ch variable, we use the following instruction `px @memory-address`

To go step by step use `ds`

#### Workflow...

The general formula for working through something like this is:

* set appropriate breakpoints
* use ds to move through instructions and check the values of register and memory
* if you make a mistake, you can always reload the program using the ood command

[Radare2 Cheatsheet](https://scoding.de/uploads/r2\_cs.pdf)

## Challenge

**IP Address:** 10.10.83.56

**Username:** elfmceager

**Password:** adventofcyber

```
ssh elfmceager@10.10.83.56
```

![](<../.gitbook/assets/image (114).png>)

![](<../.gitbook/assets/image (115).png>)

What is the value of **local\_ch** when its corresponding movl instruction is called (first if multiple)?

![](<../.gitbook/assets/image (116).png>)

![](<../.gitbook/assets/image (117).png>)

```
pdf @main
db 0x00400b51
dc
px @rbp-0xc
ds
px @rbp-0xc
```

![](<../.gitbook/assets/image (118).png>)

{% hint style="success" %}
1
{% endhint %}

What is the value of **eax** when the imull instruction is called?

```
pdf @main
db 0x00400b66
dc

```

{% hint style="success" %}
6
{% endhint %}

What is the value of **local\_4h** before **eax** is set to 0?

```
pdf @main
db 0x00400b69
dc
px @rbp-0x4
```

![](<../.gitbook/assets/image (119).png>)

{% hint style="success" %}
6
{% endhint %}
