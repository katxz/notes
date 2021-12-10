---
description: Nmap Scripting Engine
---

# NSE

{% embed url="https://nmap.org/book/nse-usage.html" %}
NSE usage and examples
{% endembed %}

{% embed url="https://nmap.org/nsedoc/index.html" %}
Detailed documentation for NSE scripts, categories and libraries.
{% endembed %}

## Usage

```
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script <filename>|<category>|<directory>|<expression>[,...]
  --script-help <filename>|<category>: Show help about scripts.
```

## Location

```
ls -l /usr/share/nmap/scripts
```

{% code title="Locate relevant scripts." %}
```
ls -l /usr/share/nmap/scripts | grep <keyword>
```
{% endcode %}

{% code title="Find usage." %}
```
nmap --script-help vuln $TARGET
nmap --script-help dns-zone-transfer $TARGET
```
{% endcode %}
