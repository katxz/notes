# Port Scanning

## Tools

{% page-ref page="../../tools/nmap/" %}



## Privileged Scans

Some scanning options need to be run with _**sudo**_ as they require access to raw sockets, which in turn require root privileges. Raw sockets allow for surgical manipulation of TCP and UDP packets. 

Without access to raw sockets, scanners such as Nmap is limited as it falls back to crafting packets by using the standard Berkeley socket API.

## Pitfalls

Penetration testers often forget to scan for open UDP ports, instead focusing on the “more exciting” TCP ports. Although UDP scanning can be unreliable, there are plenty of attack vectors lurking behind open UDP ports.

Most UDP scanners tend to use the standard “ICMP port unreachable” message to infer the status of a target port. However, this method can be completely unreliable when the target port is filtered by a firewall. In fact, in these cases the scanner will report the target port as open because of the absence of the ICMP message.

Many port scanners do not scan all available ports, and usually have a pre-set list of “interesting ports” that are scanned. This means open UDP ports can go unnoticed. Using a protocol-specific UDP port scanner may help in obtaining more accurate results.



