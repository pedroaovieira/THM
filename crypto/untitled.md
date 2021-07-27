# CrackTheHash - wip

hash-identifier

hash-analyzer [https://www.tunnelsup.com/hash-analyzer/](https://www.tunnelsup.com/hash-analyzer/)

hash-identification [https://www.onlinehashcrack.com/hash-identification.php](https://www.onlinehashcrack.com/hash-identification.php)

hashcat [https://hashcat.net/wiki/doku.php?id=example\_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)

crackstation [https://crackstation.net/](https://crackstation.net/)

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

shell5@x240:/opt/hash-identifier$ python3 hash-id.py 48bb6e862e54f2a795ffc4e541caed4d

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

```text
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
```

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

Possible Hashs: \[+\] MD5 \[+\] Domain Cached Credentials - MD4\(MD4\(\($pass\)\).\(strtolower\($username\)\)\)

Least Possible Hashs: \[+\] RAdmin v2.x \[+\] NTLM \[+\] MD4 \[+\] MD2 \[+\] MD5\(HMAC\) \[+\] MD4\(HMAC\) \[+\] MD2\(HMAC\) \[+\] MD5\(HMAC\(Wordpress\)\) \[+\] Haval-128 \[+\] Haval-128\(HMAC\) \[+\] RipeMD-128

shell5@x240:~/hack/thm/crackthehash$ hashcat -D 1 -m 0 1.txt /opt/rockyou.txt --force hashcat \(v4.0.1\) starting...

## OpenCL Platform \#1: The pocl project

* Device \#1: pthread-Intel\(R\) Core\(TM\) i5-4210U CPU @ 1.70GHz, 1024/2727 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates Rules: 1

Applicable optimizers:

* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

Password length minimum: 0 Password length maximum: 256

ATTENTION! Pure \(unoptimized\) OpenCL kernels selected. This enables cracking passwords and salts &gt; length 32 but for the price of drastical reduced performance. If you want to switch to optimized OpenCL kernels, append -O to your commandline.

Watchdog: Hardware monitoring interface not found on your system. Watchdog: Temperature abort trigger disabled. Watchdog: Temperature retain trigger disabled.

* Device \#1: build\_opts '-I /usr/share/hashcat/OpenCL -D VENDOR\_ID=64 -D CUDA\_ARCH=0 -D AMD\_ROCM=0 -D VECT\_SIZE=1 -D DEVICE\_TYPE=2 -D DGST\_R0=0 -D DGST\_R1=3 -D DGST\_R2=2 -D DGST\_R3=1 -D DGST\_ELEM=4 -D KERN\_TYPE=0 -D \_unroll'
* Device \#1: Kernel m00000\_a0.be5db123.kernel not found in cache! Building may take a while...

  Dictionary cache built:

* Filename..: /opt/rockyou.txt
* Passwords.: 14344391
* Bytes.....: 139921497
* Keyspace..: 14344384
* Runtime...: 3 secs
* Device \#1: autotuned kernel-accel to 1024
* Device \#1: autotuned kernel-loops to 1

  \[s\]tatus \[p\]ause \[r\]esume \[b\]ypass \[c\]heckpoint \[q\]uit =&gt; \[s\]tatus \[p\]ause \[r\]esume48bb6e862e54f2a795ffc4e541caed4d:easy                     

Session..........: hashcat Status...........: Cracked Hash.Type........: MD5 Hash.Target......: 48bb6e862e54f2a795ffc4e541caed4d Time.Started.....: Sat Nov 23 20:25:04 2019 \(0 secs\) Time.Estimated...: Sat Nov 23 20:25:04 2019 \(0 secs\) Guess.Base.......: File \(/opt/rockyou.txt\) Guess.Queue......: 1/1 \(100.00%\) Speed.Dev.\#1.....: 3924.3 kH/s \(0.54ms\) Recovered........: 1/1 \(100.00%\) Digests, 1/1 \(100.00%\) Salts Progress.........: 176128/14344384 \(1.23%\) Rejected.........: 0/176128 \(0.00%\) Restore.Point....: 172032/14344384 \(1.20%\) Candidates.\#1....: florian1 -&gt; 311231 HWMon.Dev.\#1.....: N/A

Started: Sat Nov 23 20:24:54 2019 Stopped: Sat Nov 23 20:25:05 2019

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

shell5@x240:~/hack/thm/crackthehash$ python3 /opt/hash-identifier/hash-id.py $\(cat 2.txt\)

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

```text
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
```

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

Possible Hashs: \[+\] SHA-1 \[+\] MySQL5 - SHA-1\(SHA-1\($pass\)\)

Least Possible Hashs: \[+\] Tiger-160

shell5@x240:~/hack/thm/crackthehash$ hashcat -D 1 -m 100 2.txt /opt/rockyou.txt --force hashcat \(v4.0.1\) starting...

## OpenCL Platform \#1: The pocl project

* Device \#1: pthread-Intel\(R\) Core\(TM\) i5-4210U CPU @ 1.70GHz, 1024/2727 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates Rules: 1

Applicable optimizers:

* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

Password length minimum: 0 Password length maximum: 256

ATTENTION! Pure \(unoptimized\) OpenCL kernels selected. This enables cracking passwords and salts &gt; length 32 but for the price of drastical reduced performance. If you want to switch to optimized OpenCL kernels, append -O to your commandline.

Watchdog: Hardware monitoring interface not found on your system. Watchdog: Temperature abort trigger disabled. Watchdog: Temperature retain trigger disabled.

* Device \#1: build\_opts '-I /usr/share/hashcat/OpenCL -D VENDOR\_ID=64 -D CUDA\_ARCH=0 -D AMD\_ROCM=0 -D VECT\_SIZE=1 -D DEVICE\_TYPE=2 -D DGST\_R0=3 -D DGST\_R1=4 -D DGST\_R2=2 -D DGST\_R3=1 -D DGST\_ELEM=5 -D KERN\_TYPE=100 -D \_unroll'
* Device \#1: Kernel m00100\_a0.be410c43.kernel not found in cache! Building may take a while...

  Dictionary cache hit:

* Filename..: /opt/rockyou.txt
* Passwords.: 14344384
* Bytes.....: 139921497
* Keyspace..: 14344384
* Device \#1: autotuned kernel-accel to 1024
* Device \#1: autotuned kernel-loops to 1

  \[s\]tatus \[p\]ause \[r\]esume \[b\]ypass \[c\]heckpoint \[q\]uit =&gt; \[s\]tatus \[p\]ause \[r\]esumecbfdac6008f9cab4083784cbd1874f76618d2a97:password123      

Session..........: hashcat Status...........: Cracked Hash.Type........: SHA1 Hash.Target......: cbfdac6008f9cab4083784cbd1874f76618d2a97 Time.Started.....: Sat Nov 23 20:29:22 2019 \(0 secs\) Time.Estimated...: Sat Nov 23 20:29:22 2019 \(0 secs\) Guess.Base.......: File \(/opt/rockyou.txt\) Guess.Queue......: 1/1 \(100.00%\) Speed.Dev.\#1.....: 5535.1 kH/s \(0.65ms\) Recovered........: 1/1 \(100.00%\) Digests, 1/1 \(100.00%\) Salts Progress.........: 4096/14344384 \(0.03%\) Rejected.........: 0/4096 \(0.00%\) Restore.Point....: 0/14344384 \(0.00%\) Candidates.\#1....: 123456 -&gt; oooooo HWMon.Dev.\#1.....: N/A

Started: Sat Nov 23 20:29:14 2019 Stopped: Sat Nov 23 20:29:24 2019

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

shell5@x240:~/hack/thm/crackthehash$ python3 /opt/hash-identifier/hash-id.py $\(cat 3.txt\)

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

\*\*\*\*

```text
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
```

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

Possible Hashs: \[+\] SHA-256 \[+\] Haval-256

Least Possible Hashs: \[+\] GOST R 34.11-94 \[+\] RipeMD-256 \[+\] SNEFRU-256 \[+\] SHA-256\(HMAC\) \[+\] Haval-256\(HMAC\) \[+\] RipeMD-256\(HMAC\) \[+\] SNEFRU-256\(HMAC\) \[+\] SHA-256\(md5\($pass\)\)

### \[+\] SHA-256\(sha1\($pass\)\)

shell5@x240:~/hack/thm/crackthehash$ hashcat -D 1 -m 1400 3.txt /opt/rockyou.txt --force hashcat \(v4.0.1\) starting...

## OpenCL Platform \#1: The pocl project

* Device \#1: pthread-Intel\(R\) Core\(TM\) i5-4210U CPU @ 1.70GHz, 1024/2727 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates Rules: 1

Applicable optimizers:

* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

Password length minimum: 0 Password length maximum: 256

ATTENTION! Pure \(unoptimized\) OpenCL kernels selected. This enables cracking passwords and salts &gt; length 32 but for the price of drastical reduced performance. If you want to switch to optimized OpenCL kernels, append -O to your commandline.

Watchdog: Hardware monitoring interface not found on your system. Watchdog: Temperature abort trigger disabled. Watchdog: Temperature retain trigger disabled.

* Device \#1: build\_opts '-I /usr/share/hashcat/OpenCL -D VENDOR\_ID=64 -D CUDA\_ARCH=0 -D AMD\_ROCM=0 -D VECT\_SIZE=1 -D DEVICE\_TYPE=2 -D DGST\_R0=3 -D DGST\_R1=7 -D DGST\_R2=2 -D DGST\_R3=6 -D DGST\_ELEM=8 -D KERN\_TYPE=1400 -D \_unroll'
* Device \#1: Kernel m01400\_a0.eae61ac5.kernel not found in cache! Building may take a while...

  Dictionary cache hit:

* Filename..: /opt/rockyou.txt
* Passwords.: 14344384
* Bytes.....: 139921497
* Keyspace..: 14344384
* Device \#1: autotuned kernel-accel to 1024
* Device \#1: autotuned kernel-loops to 1

  \[s\]tatus \[p\]ause \[r\]esume \[b\]ypass \[c\]heckpoint \[q\]uit =&gt; \[s\]tatus \[p\]ause \[r\]esume1c8bfe8f801d79745c4631d09fff36c82aa37fc4cce4fc946683d7b336b63032:letmein

Session..........: hashcat Status...........: Cracked Hash.Type........: SHA-256 Hash.Target......: 1c8bfe8f801d79745c4631d09fff36c82aa37fc4cce4fc94668...b63032 Time.Started.....: Sat Nov 23 20:35:27 2019 \(0 secs\) Time.Estimated...: Sat Nov 23 20:35:27 2019 \(0 secs\) Guess.Base.......: File \(/opt/rockyou.txt\) Guess.Queue......: 1/1 \(100.00%\) Speed.Dev.\#1.....: 3404.8 kH/s \(1.12ms\) Recovered........: 1/1 \(100.00%\) Digests, 1/1 \(100.00%\) Salts Progress.........: 4096/14344384 \(0.03%\) Rejected.........: 0/4096 \(0.00%\) Restore.Point....: 0/14344384 \(0.00%\) Candidates.\#1....: 123456 -&gt; oooooo HWMon.Dev.\#1.....: N/A

Started: Sat Nov 23 20:35:19 2019 Stopped: Sat Nov 23 20:35:29 2019

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

## 4

shell5@x240:~/hack/thm/crackthehash$ hashid $\(cat 4.txt\) Analyzing '$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom' \[+\] Blowfish\(OpenBSD\) \[+\] Woltlab Burning Board 4.x \[+\] bcrypt

shell5@x240:~/hack/thm/crackthehash$ hashcat -D 1 -m 3200 4.txt /opt/rockyou.txt --force hashcat \(v4.0.1\) starting...

## OpenCL Platform \#1: The pocl project

* Device \#1: pthread-Intel\(R\) Core\(TM\) i5-4210U CPU @ 1.70GHz, 1024/2727 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates Rules: 1

Applicable optimizers:

* Zero-Byte
* Single-Hash
* Single-Salt

Password length minimum: 0 Password length maximum: 72

Watchdog: Hardware monitoring interface not found on your system. Watchdog: Temperature abort trigger disabled. Watchdog: Temperature retain trigger disabled.

* Device \#1: build\_opts '-I /usr/share/hashcat/OpenCL -D VENDOR\_ID=64 -D CUDA\_ARCH=0 -D AMD\_ROCM=0 -D VECT\_SIZE=8 -D DEVICE\_TYPE=2 -D DGST\_R0=0 -D DGST\_R1=1 -D DGST\_R2=2 -D DGST\_R3=3 -D DGST\_ELEM=6 -D KERN\_TYPE=3200 -D \_unroll'

  Dictionary cache built:

* Filename..: dict.txt
* Passwords.: 1
* Bytes.....: 5
* Keyspace..: 1
* Runtime...: 0 secs
* Device \#1: autotuned kernel-accel to 2
* Device \#1: autotuned kernel-loops to 4

  \[s\]tatus \[p\]ause \[r\]esume \[b\]ypass \[c\]heckpoint \[q\]uit =&gt; The wordlist or mask that you are using is too small.

  This means that hashcat cannot use the full parallel power of your device\(s\).

  Unless you supply more work, your cracking speed will drop.

  For tips on supplying more work, see: [https://hashcat.net/faq/morework](https://hashcat.net/faq/morework)

Approaching final keyspace - workload adjusted.

$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom:bleh

Session..........: hashcat Status...........: Cracked Hash.Type........: bcrypt $2\*$, Blowfish \(Unix\) Hash.Target......: $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX...8wsRom Time.Started.....: Sat Nov 23 20:48:18 2019 \(1 sec\) Time.Estimated...: Sat Nov 23 20:48:19 2019 \(0 secs\) Guess.Base.......: File \(dict.txt\) Guess.Queue......: 1/1 \(100.00%\) Speed.Dev.\#1.....: 0 H/s \(0.37ms\) Recovered........: 1/1 \(100.00%\) Digests, 1/1 \(100.00%\) Salts Progress.........: 1/1 \(100.00%\) Rejected.........: 0/1 \(0.00%\) Restore.Point....: 0/1 \(0.00%\) Candidates.\#1....: bleh -&gt; bleh HWMon.Dev.\#1.....: N/A

Started: Sat Nov 23 20:48:18 2019 Stopped: Sat Nov 23 20:48:20 2019

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

## 5

shell5@x240:~/hack/thm/crackthehash$ python3 /opt/hash-identifier/hash-id.py $\(cat 5.txt\)

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

\*\*\*\*

```text
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
```

## 

**\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#**

Possible Hashs: \[+\] MD5 \[+\] Domain Cached Credentials - MD4\(MD4\(\($pass\)\).\(strtolower\($username\)\)\)

Least Possible Hashs: \[+\] RAdmin v2.x \[+\] NTLM

