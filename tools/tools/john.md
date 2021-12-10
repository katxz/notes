# John

Cheat sheet: [http://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats](http://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats)

```
$ john --format=NT \
  --wordlist=/usr/share/wordlists/rockyou.txt \
  hash.txt
  
  $ john --format=NT hash.txt --show
```
