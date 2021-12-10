# Port Scanning

## Tools

{% content-ref url="../../tools/tools/nmap/" %}
[nmap](../../tools/tools/nmap/)
{% endcontent-ref %}

## Current Process

```
# Autorecon
sudo autorecon $TARGET

# Nmap TCP IP range / subnet (lots of targets, quick high level scan)
nmap -v -A -Pn --top-ports 2000 $TARGET

# Nmap UDP (lots of targets, quick high level scan)
sudo nmap -sU -Pn --top-ports 2000 $TARGET --open

# More thorough scan on a single targert
nmap -v -A <-n> -p- -oG [output-file-name] [target-ip]
```

{% hint style="info" %}
When `autorecon` results seems inconsistent to observed behaviour with Nmap / manual enumeration, re-run it, could be caused by a transient error.
{% endhint %}

## UDP Port Scanning

{% hint style="info" %}
The result of UDP scans can be quite unreliable. Make sure to do the top ports a few times to confirm the findings.
{% endhint %}

{% hint style="info" %}
Given the open|filtered UDP ports some poking as well. They may still be valuable targets. (Unless all the ports return open|filtered then probably not worth the time unless there really isn't any other way in).
{% endhint %}

## Privileged Scans

Some scanning options need to be run with _**sudo**_ as they require access to raw sockets, which in turn require root privileges. Raw sockets allow for surgical manipulation of TCP and UDP packets.&#x20;

Without access to raw sockets, scanners such as Nmap is limited as it falls back to crafting packets by using the standard Berkeley socket API.

## Pitfalls

Penetration testers often forget to scan for open UDP ports, instead focusing on the “more exciting” TCP ports. Although UDP scanning can be unreliable, there are plenty of attack vectors lurking behind open UDP ports.

Most UDP scanners tend to use the standard “ICMP port unreachable” message to infer the status of a target port. However, this method can be completely unreliable when the target port is filtered by a firewall. In fact, in these cases the scanner will report the target port as open because of the absence of the ICMP message.

Many port scanners do not scan all available ports, and usually have a pre-set list of “interesting ports” that are scanned. This means open UDP ports can go unnoticed. Using a protocol-specific UDP port scanner may help in obtaining more accurate results.

