# Uncommon SUID Files

```text
strings <binary>
```

```text
# background the binary process first
ps -eo pid,ppid,args | grep <pid>
```

```text
strace <binary> 2>&1 | grep -i -E "open|access|no such file"
```



