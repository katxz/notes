# 111 rpcbind

rpcbind is just a server that converts remote procedure call (RPC) program number into universal addresses. When an RPC service is started, it tells rpcbind the address at which it is listening and the RPC program number it is prepared to serve.&#x20;

In some cases port 111 is access to a network file system. Can use nmap to enumerate it.

```
nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount <ip>
```
