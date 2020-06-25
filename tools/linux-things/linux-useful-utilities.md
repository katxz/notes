# Linux Useful Utilities

## **openssl \(create self-signed certificate\)**

Create a self-signed certificate using openssl for `socat`:

```text
openssl req -newkey rsa:2048 -nodes -keyout bind_shell.key -x509 -days 362 -out bind_shell.crt
```

* `req` command along with the `-x509` option creates self-signed certificates
* `-newkey` will generates a new private key
* `rsa:2048` specifies RSA encryption with 2048 key length
* `-nodes` \(no des\) will store the private key unencrypted
* `-keyout` will save the key to a file
* `-days` specifies the validity period
* `-out` will save the certificate to a file

Now that the key and certificate have been generated, we first need to convert them to a format `socat` will accept. 

To do so, we combine both the `bind_shell.key` and `bind_shell.crt` files into a single `.pem` file before we create the encrypted `socat` listener.

```text
cat bind_shell.key bind_shell.crt > bind_shell.pem
```

## **shasum \| md5sum**

```text
shasum -a256 file.txt
```

```text
md5sum file.txt
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

