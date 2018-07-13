### Level 0

#### Level Goal
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

#### Commands you may need to solve this level
`ssh`
### Solve
```shell
$ ssh -p 2220  bandit0@bandit.labs.overthewire.org
$ password: bandi0
```
***

### Level 0 → Level 1

#### Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit0@bandit.labs.overthewire.org
$ password: bandi0
$ find -name readme -exec cat {} \;
```

**found password:** boJ9jbbUNNfktd78OOpsqOltutMc3MY1

***

### Level 1 → Level 2

#### Level Goal
The password for the next level is stored in a file called - located in the home directory

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit1@bandit.labs.overthewire.org
$ password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
$ find -name * -exec cat {} \;
```

**found password:** CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

***

### Level 2 → Level 3

#### Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit2@bandit.labs.overthewire.org
$ password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

**found password:** UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

***

### Level 3 → Level 4

#### Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit3@bandit.labs.overthewire.org
$ password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
$ find ./inhere/ -exec cat {} \;
```
**found password:** pIwrPrtPN36QITSp3EQaw936yaFoFgAB

***

### Level 4 → Level 5

#### Level Goal
The password for the next level is  stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit4@bandit.labs.overthewire.org
$ password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
$ find ./inhere/ -exec file {} \;
./inhere/: directory
./inhere/-file08: data
./inhere/-file05: data
./inhere/-file07: ASCII text
./inhere/-file04: data
./inhere/-file00: data
./inhere/-file01: data
./inhere/-file06: data
./inhere/-file03: data
./inhere/-file09: data
./inhere/-file02: data
$ cat ./inhere/-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

**found password:** koReBOKuIDDepwhWk7jZC0RTdopnAYKh

***

### Level 5 → Level 6

#### Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
*   human-readable
*   1033 bytes in size
*   not executable

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find`

### Solve
```shell
$ ssh -p 2220  bandit5@bandit.labs.overthewire.org
$ password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
$ find ./inhere/ -size 1033c -exec file {} \;
./inhere/maybehere07/.file2: ASCII text, with very long lines
$ cat ./inhere/maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

**found password:** DXjZPULLxYr17uwoI01bNLQbtFemEgo7

***

### Level 6 → Level 7

#### Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
*   owned by user bandit7
*   owned by group bandit6
*   33 bytes in size

#### Commands you may need to solve this level
`ls, cd, cat, file, du, find, grep`

### Solve
```shell
$ ssh -p 2220  bandit6@bandit.labs.overthewire.org
$ password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
$ find / -user bandit7 -size 33c 2>/dev/null | xargs cat
cat: /etc/bandit_pass/bandit7: Permission denied
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

**found password:** HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

***

### Level 7 → Level 8

#### Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

#### Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

### Solve
```shell
$ ssh -p 2220  bandit7@bandit.labs.overthewire.org
$ password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
$ grep -e ^millionth  data.txt
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
**found password:** cvX2JJa4CFALtqS87jk27qwqGhBM9plV

***

### Level 8 → Level 9

#### Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

#### Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

### Solve
```shell
$ ssh -p 2220  bandit8@bandit.labs.overthewire.org
$ password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV
$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
**found password:** UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

***

### Level 9 → Level 10

#### Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.

#### Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

### Solve
```shell
$ ssh -p 2220  bandit9@bandit.labs.overthewire.org
$ password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
$ strings data.txt | grep ^=
========== password
========== ism
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

**found password:** truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

***

### Level 10 → Level 11

#### Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

#### Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

### Solve
```shell
$ ssh -p 2220  bandit10@bandit.labs.overthewire.org
$ password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
**found password:** IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

***

### Level 11 → Level 12

#### Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

#### Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

### Solve
```shell
$ ssh -p 2220  bandit11@bandit.labs.overthewire.org
$ password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
$ cat data.txt | tr '[a-z][A-Z]' '[n-za-m][N-ZA-M]'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```
**found password:** 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

***

### Level 12 → Level 13

#### Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

#### Commands you may need to solve this level
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv

### Solve
```shell
$ ssh -p 2220  bandit12@bandit.labs.overthewire.org
$ password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
$ ...
$ gunzip -d data8.gz
$ cat data8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

```

**found password:** 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

***

### Level 13 → Level 14

#### Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

#### Commands you may need to solve this level
`ssh, telnet, nc, openssl, s_client, nmap`

### Solve
```shell
$ ssh -p 2220  bandit13@bandit.labs.overthewire.org
$ password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
$ $ cat sshkey.private
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----
```

**found password:** add private key to localhost

***

### Level 14 → Level 15

#### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

#### Commands you may need to solve this level
`ssh, telnet, nc, openssl, s_client, nmap`

### Solve
```shell
$ ssh -p 2220 -i ~/.ssh/wargame bandit14@bandit.labs.overthewire.org
$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
$ nc localhost 30000
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

**found password:** BfMYroe26WYalil77FoDi9qh59eK5xNr

***

### Level 15 → Level 16

#### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

#### Commands you may need to solve this level
`ssh, telnet, nc, openssl, s_client, nmap`

### Solve
```shell
$ ssh -p 2220 bandit15@bandit.labs.overthewire.org
$ password BfMYroe26WYalil77FoDi9qh59eK5xNr
$ $ openssl s_client -connect localhost:30001  -ign_eof
CONNECTED(00000003)
depth=0 CN = li190-250.members.linode.com
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = li190-250.members.linode.com
verify return:1
---
Certificate chain
 0 s:/CN=li190-250.members.linode.com
   i:/CN=li190-250.members.linode.com
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIC3jCCAcagAwIBAgIJAI5QiWZw4YHbMA0GCSqGSIb3DQEBCwUAMCcxJTAjBgNV
BAMTHGxpMTkwLTI1MC5tZW1iZXJzLmxpbm9kZS5jb20wHhcNMTQxMTE0MTAyODA0
WhcNMjQxMTExMTAyODA0WjAnMSUwIwYDVQQDExxsaTE5MC0yNTAubWVtYmVycy5s
aW5vZGUuY29tMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAsKmy9o5z
WU+1EH7Z3bB5TGQA+16zXDcEJy6tZWZ8CDrRyQXiahendp45BWUc/ZuLDo0+B3Wt
ZXjofmLw/F4fmR+8X1s1fQZX2dFt920qEm7LxqzWd0c7FdHiBwwRrwhkk+3cQpOB
TTGdLWEgpdmwwNZDTUdsDLzjDczPnju6T6p6ArTECztPbmTjfY4QIRtC6capL1Z+
yPJSQVAuAMEX1wTDWTGdm0VV7oW4F5cGZutf6QAP51jdhSyZuGilIPHbnj0l6Qc7
a7+OtEsEGi31aJ8KpRf7LNZ7DXCuoB3Hf75Pd6VjDgoOIagcH0NYqa75gEjBkGzs
ktLWykT7ag7fKwIDAQABow0wCzAJBgNVHRMEAjAAMA0GCSqGSIb3DQEBCwUAA4IB
AQCaZdUNAj8WDEKWdoU3LNXUBJlTJwiWBrh550PbHSQORcCz2K0kiMei1A4ojK2N
dMHFGAqAeUEaxtz92p2BoFpZasAtdSa3u63tBckFhfUolIS1TC7Cj51y19ysTeep
fGPFpuPCVqVPsruei8Z/iqn3bFIhQQdmumeePZQdPMwZSWHNVYC5XODd7PvNDrDu
5MZJjkz4+6LbwwAvyew62meFN2QEsYbK2Brtbhze+IjE27FGWlSw4K3jlwa409MD
MTf4JU41ELaYY8G/LSNDJsBVhhkHzvXR9iCbXxNz3IL0dQDNj7h4LKhBy0q7hvqg
kDzwlmBO4WKSmCAuky44cXmd
-----END CERTIFICATE-----
subject=/CN=li190-250.members.linode.com
issuer=/CN=li190-250.members.linode.com
---
No client certificate CA names sent
---
SSL handshake has read 1714 bytes and written 637 bytes
---
New, TLSv1/SSLv3, Cipher is DHE-RSA-AES256-SHA
Server public key is 2048 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
SSL-Session:
    Protocol  : SSLv3
    Cipher    : DHE-RSA-AES256-SHA
    Session-ID: 359ED4AED719136500F5404A85986BF94B085AE197A04CCEC9CCB440E95180F2
    Session-ID-ctx:
    Master-Key: B4809EBB497F38315E01AA9D76315F27910A425FFAD5AF297024C2687AAF8D440D37C67B7AFA05C0C76F8F084F91245F
    Key-Arg   : None
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    Start Time: 1496093746
    Timeout   : 300 (sec)
    Verify return code: 18 (self signed certificate)
---
BfMYroe26WYalil77FoDi9qh59eK5xNr
Correct!
cluFn7wTiGryunymYOu4RcffSxQluehd
```

**found password:** cluFn7wTiGryunymYOu4RcffSxQluehd

***

### Level 16 → Level 17

#### Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

#### Commands you may need to solve this level
`ssh, telnet, nc, openssl, s_client, nmap`

### Solve
```shell
$ ssh -p 2220 bandit15@bandit.labs.overthewire.org
$ password cluFn7wTiGryunymYOu4RcffSxQluehd
$ nmap -p 31000-32000 localhost

Starting Nmap 6.40 ( http://nmap.org ) at 2017-05-29 21:50 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00038s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown
$ openssl s_client -connect localhost:31790 -ign_eof
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY----
```

**found password:** Add private key

***

### Level 17 → Level 18

#### Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

#### Commands you may need to solve this level
`cat, grep, ls, diff`

### Solve
```shell
$ ssh -p 2220 -i ~/.ssh/wargame17 bandit17@bandit.labs.overthewire.org
$ password: no any password, use rsa key!
$ diff passwords.new passwords.old
42c42
< kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
---
> BS8bqB1kqkinKJjuxL6k072Qq9NRwQpR
```
**found password:** BS8bqB1kqkinKJjuxL6k072Qq9NRwQpR

***

### Level 18 → Level 19

#### Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

#### Commands you may need to solve this level
`cat, grep, ls, diff`


### Solve
```shell
$ ssh -p 2220 bandit18@bandit.labs.overthewire.org
$ password: BS8bqB1kqkinKJjuxL6k072Qq9NRwQpR
$ diff passwords.old passwords.new
42c42
< BS8bqB1kqkinKJjuxL6k072Qq9NRwQpR
---
> kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```

**found password:** kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

***

### Level 18 → Level 19

#### Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

#### Commands you may need to solve this level
`ssh, ls, cat`

### Solve
```shell
$ ssh -p 2220 bandit19@bandit.labs.overthewire.org cat readme
$ password: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```

**found password:** IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

***

### Level 19 → Level 20

#### Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

#### Commands you may need to solve this level
`NO ONE CAN HELP YOU.`


### Solve
```shell
$ ssh -p 2220 bandit19@bandit.labs.overthewire.org cat readme
$ password: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
$ ./bandit20-do cat /etc/bandit_pass/bandit20
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```

**found password:** GbKksEFF4yrVs6il55v6gwY5aVje5f0j

***

### Level 20 → Level 21

#### Level Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: To beat this level, you need to login twice: once to run the setuid command, and once to start a network daemon to which the setuid will connect.

NOTE 2: Try connecting to your own network daemon to see if it works as you think

#### Commands you may need to solve this level
`ssh, nc, cat`

### Solve
```shell
$ ssh -p 2220 bandit20@bandit.labs.overthewire.org
$ password: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
$ nc -l 30123
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
$ ./suconnect 30123
```
**found password:** gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr

### Level 21 → Level 22

#### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

#### Commands you may need to solve this level
`cron, crontab, crontab(5) (use “man 5 crontab” to access this)`

### Solve
```shell
$ ssh -p 2220 bandit21@bandit.labs.overthewire.org
$ password: gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
$ run-parts /etc/cron.d/                  
bandit21@melinda:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
```
**found password:** Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI

***

### Level 22 → Level 23

#### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

#### Commands you may need to solve this level
`cron, crontab, crontab(5) (use “man 5 crontab” to access this)`

***

### Solve
```shell
$ ssh -p 2220 bandit22@bandit.labs.overthewire.org
$ password: Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
```

**found password:** jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n

***

### Level 23 → Level 24

#### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

#### Commands you may need to solve this level
`cron, crontab, crontab(5) (use “man 5 crontab” to access this)`

### Solve
```shell
$ ssh -p 2220 bandit23@bandit.labs.overthewire.org
$ password: jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
$ echo "cat /etc/bandit_pass/bandit24 > /tmp/tmp.UIIUtLy8Kp" > /var/spool/bandit24/go.sh
$ chmod +x /var/spool/bandit24/go.sh
$ watch cat /tmp/tmp.UIIUtLy8Kp

```

**found password:** UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ

***

### Level 24 → Level 25

#### Level Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

### Solve
```shell
$ ssh -p 2220 bandit24@bandit.labs.overthewire.org
$ password: UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
$ for i in `seq 1 10000`; do  echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i >> /tmp/tmp.7MXaT9NglI ; done
$ nc localhost 30002 < /tmp/tmp.7MXaT9NglI | grep ^[^Wrong]
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
Exiting.
```

**found password:** uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

***

### Level 25 → Level 26

#### Level Goals
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

#### Commands you may need to solve this level
`ssh, cat, more, vi, ls, id, pwd`

### Solve
```shell
$ ssh -p 2220 bandit25@bandit.labs.overthewire.org
$ password: uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
$ cat /etc/passwd | grep  bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
$ cat /etc/passwd | grep  bandit25
bandit25:x:11025:11025:bandit level 25:/home/bandit25:/bin/bash
$ cat bandit26.sshkey
-----BEGIN RSA PRIVATE KEY-----
```

**found password:** use ssh key

***

### Level 26 → Level 27

#### Level Goals
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.
