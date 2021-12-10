# 21 - FTP

{% hint style="success" %}
Don't forget browsing from your favourite browser can be easier than using a CLI client.
{% endhint %}

## FileZilla Password Files

* `C:\Program Files (x86)\FileZilla Server\FileZilla Server.xml`
* `C:\Program Files\FileZilla Server\FileZilla Server.xml`

## Making Connection

```
nc <ip> 21
```

```
> ftp <ip>
User: username
Passowrd:passwd123!

ftp> binary
200 Type set to: Binary.

ftp> get test.exe

ftp> bye
```

