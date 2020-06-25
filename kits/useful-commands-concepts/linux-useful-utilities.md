# Linux Useful Utilities

## **shasum**

```text
shasum -a256 file.txt
```

## **hex viewer**

### **xxd**

```text
xxd badchars.bin
```

### **hexdump**

```text
hexdump -C badchars.bin
```

### **vim**

\(don't use as this may accidentally write changes to the file\)

```text
:%!xxd to switch into hex mode
:%!xxd -r to exit from hex mode
:%!hexdump -C
```

