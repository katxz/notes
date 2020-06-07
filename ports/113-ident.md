# 113 - ident

## Basic Information

Is an Internet protocol that helps identify the user of a particular TCP connection.

* https://en.wikipedia.org/wiki/Ident\_protocol
* https://tools.ietf.org/html/rfc1413

**Default port:** 113

```text
PORT    STATE SERVICE
113/tcp open  ident
```

## Demo

If a machine is running the service ident and samba \(445\) and you are connected to samba using the port 43218. You can get which user is running the samba service by doing:

```text
$ nc -nv 10.11.1.136 445
(UNKNOWN) [10.11.1.136] 445 (microsoft-ds) open

$ ss -ntup
Netid  State  Recv-Q  Send-Q         Local Address:Port       Peer Address:Port   Process     
tcp    ESTAB       0       0      192.168.119.189:45530         10.11.1.136:445   users:(("nc",pid=49944,fd=3))

$ nc -nv 10.11.1.136 113
(UNKNOWN) [10.11.1.136] 113 (auth) open
445,45530
445 , 45530 : USERID : UNIX :root
```

## Scripts

ident-user-enum: [https://tools.kali.org/information-gathering/ident-user-enum](https://tools.kali.org/information-gathering/ident-user-enum)

## Nmap

By default \(-sC\) nmap will identify every user of every running port:

```text
PORT    STATE SERVICE     VERSION
22/tcp  open  ssh         OpenSSH 4.3p2 Debian 9 (protocol 2.0)
|_auth-owners: root
| ssh-hostkey: 
|   1024 88:23:98:0d:9d:8a:20:59:35:b8:14:12:14:d5:d0:44 (DSA)
|_  2048 6b:5d:04:71:76:78:56:96:56:92:a8:02:30:73:ee:fa (RSA)
113/tcp open  ident
|_auth-owners: identd
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: LOCAL)
|_auth-owners: root
445/tcp open  netbios-ssn Samba smbd 3.0.24 (workgroup: LOCAL)
|_auth-owners: root
```

## Shodan

`oident`

## Files

identd.conf

