# mssqlclient.py \(Impacket\)

```text
mssqlclient.py DOMAIN/user@ip -windows-auth
```

```text
mssqlclient.py user@ip
```

{% hint style="info" %}
Note if backslash `\` is used by accident `mssqlclient.py` will fail to parse `user` value and use `DOMAIN/Guest` user by default.
{% endhint %}

{% page-ref page="../ports/1433-mssql.md" %}



