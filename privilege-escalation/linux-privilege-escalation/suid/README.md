# SUID

## Find SUID files

```
find / -perm -u=s -type f 2>/dev/null
```

```
find / -perm /4000 2>&1 | grep -v “Permission denied”
```

## Others

```
strings <binary>
```

```
# background the binary process first
ps -eo pid,ppid,args | grep <pid>
```

```
strace <binary> 2>&1 | grep -i -E "open|access|no such file"
```

