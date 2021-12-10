# 80 | 443 - HTTP(S)

{% embed url="https://github.com/maurosoria/dirsearch" %}

{% embed url="https://github.com/OJ/gobuster" %}

```
$ gobuster dir -u http://1.2.3.4:4444/internal \
  -w /usr/share/wordlist/dirbuster/wordlist.txt | tee target.log
```
