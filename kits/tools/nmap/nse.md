---
description: Nmap Scripting Engine
---

# NSE

{% embed url="https://nmap.org/book/nse-usage.html" caption="NSE usage and examples" %}

{% embed url="https://nmap.org/nsedoc/index.html" caption="Detailed documentation for NSE scripts, categories and libraries." %}

## Usage

```text
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script <filename>|<category>|<directory>|<expression>[,...]
  --script-help <filename>|<category>: Show help about scripts.
```

## Location

```text
ls -l /usr/share/nmap/scripts
```

{% code title="Locate relevant scripts." %}
```text
ls -l /usr/share/nmap/scripts | grep <keyword>
```
{% endcode %}

{% code title="Find usage." %}
```text
nmap --script-help vuln $TARGET
nmap --script-help dns-zone-transfer $TARGET
```
{% endcode %}

