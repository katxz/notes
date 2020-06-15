# Windows Commands

## icacls \| cacls

```text
# Older Windows
C:\> cacls example.py
C:\example.py NT AUTHORITY\SYSTEM:F 
              BUILTIN\Administrators:F 
              BUILTIN\Users:R 


# Newer Windows
C:\>icacls example.pl
C:\example.pl BUILTIN\Administrators:(ID)F 
              NT AUTHORITY\SYSTEM:(ID)F 
              BUILTIN\Users:(ID)R 
              NT AUTHORITY\Authenticated Users:(ID)C 

```



