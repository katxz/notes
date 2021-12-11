# SUID

## Find SUID files

```
find / -perm -u=s -type f 2>/dev/null
```

```
find / -perm /4000 2>&1 | grep -v “Permission denied”
```

Analyse custom SUID files

```
strings <binary>
```

Note if these SUID binaries are calling programs without full path (e.g. noticed from `strings` command output), we can potentially use Path Hijacking to hijack the relative paths (i.e. create another executable with identical name and add it to `PATH`).

## Others

```
# background the binary process first
ps -eo pid,ppid,args | grep <pid>
```

```
strace <binary> 2>&1 | grep -i -E "open|access|no such file"
```

