# SShuttle

## Install and Usage

```text
$ sudo pip install sshuttle
$ sshuttle -r user@host subnet
```

## Example

```text
$ sshuttle -r user@10.11.1.x 10.1.1.0/24
[local sudo] Password:                                                                                                                                                  
user@10.11.1.x's password: 
client: Connected.
```

## Note

sshuttle w/ nmap may show that every single port is open. Use proxychains with -sT instead.

