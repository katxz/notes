---
description: 'Nmap: the Network Mapper'
---

# Nmap

{% embed url="https://nmap.org/" caption="The official Nmap website" %}

{% embed url="https://tools.kali.org/information-gathering/nmap" caption="Kali Nmap package description" %}

## Examples

{% code title="SYN scan on 200 most common ports, no ping or DNS." %}
```text
nmap -Pn --top-ports 200 $TARGET --open
```
{% endcode %}

{% code title="SYN scan on 1000 most common ports, no ping or DNS." %}
```text
nmap -Pn $TARGET --open
```
{% endcode %}

{% code title="SYN scan on all open ports, no ping or DNS." %}
```text
nmap -p- -Pn $TARGET --open 
```
{% endcode %}

{% hint style="info" %}
 SYN or half open scan is the default. It is fast and can be used with **-p-** option. 
{% endhint %}

{% code title="Connect scan on 1000 most common ports, no ping or DNS." %}
```text
nmap -sT -Pn $TARGET --open
```
{% endcode %}

{% hint style="info" %}
Connect scan should be used when scanning via [proxychains](https://github.com/haad/proxychains). 
{% endhint %}

{% code title="UDP scan on 200 most common ports, privileged scan." %}
```text
sudo nmap -sU -Pn --top-ports 200 $TARGET --open
```
{% endcode %}

{% hint style="info" %}
UDP scan is unreliable and slow but should be included for a thorough enumeration.
{% endhint %}

{% hint style="info" %}
The result of UDP scans can be quite unreliable. Make sure to do the top ports a few times to confirm the findings.
{% endhint %}

{% hint style="info" %}
Given the open\|filtered UDP ports some poking as well. They may still be valuable targets.
{% endhint %}

{% code title="Script scan and service/version detection on specified ports." %}
```text
nmap -p21,22,80 -sC -sV $TARGET
```
{% endcode %}

{% code title="Script scan known vulnerabilities on specified ports." %}
```text
nmap -p21,22,80 --script vuln $TARGET
```
{% endcode %}

{% code title="Script scan and service/version detection for responsive ports." %}
```text
ports=$(nmap -p- --min-rate=1000 -T4 $TARGET | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)
nmap -sC -sV -p$ports $TARGET 
```
{% endcode %}

## Frequently Used Options

{% embed url="https://nmap.org/book/man-briefoptions.html" caption="Brief man page summary" %}

{% embed url="https://nmap.org/book/man.html" caption="Detailed man page summary" %}

```text
Nmap 7.80 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
```

```text
MISC:
  -V: Print version number
  -h: Print this help summary page.
```

```text
SCAN TECHNIQUES:
  -sS/sT: TCP SYN/Connect() scans -- the default scan type
  -sU: UDP Scan

HOST DISCOVERY:
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
    i.e. do not ping + never do DNS resolution
```

```text
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script <filename>|<category>|<directory>|<expression>[,...]
  --script-help <filename>|<category>: Show help about scripts.
```

```text
PORT SPECIFICATION AND SCAN ORDER:
  <DEFAULT>: Scan 1000 most common ports
  -p <port ranges>: Only scan specified ports
    Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
  -p-: Scan all ports
  --exclude-ports <port ranges>: Exclude the specified ports from scanning
  --top-ports <number>: Scan <number> most common ports
  --open: Only show open (or possibly open) ports\
```

{% hint style="info" %}
To find more information on the most common ports:

`$ less /usr/share/nmap/nmap-services`
{% endhint %}

```text
SERVICE/VERSION DETECTION:
  -sV: Probe open ports to determine service/version info

OS DETECTION:
  -O: Enable OS detection

ALL IN ONE:
  -A: Enable OS detection, version detection, script scanning, and traceroute
```

```text
OUTPUT:
  -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3,
     and Grepable format, respectively, to the given filename.
  -oA <basename>: Output in the three major formats at once
  -v: Increase verbosity level (use -vv or more for greater effect)
  -d: Increase debugging level (use -dd or more for greater effect)
  --reason: Display the reason a port is in a particular state
```

```text
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  
  -iL <inputfilename>: Input from list of hosts/networks
  --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
  --excludefile <exclude_file>: Exclude list from file
```

