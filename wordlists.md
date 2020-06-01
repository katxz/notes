# Wordlists

## Kali Wordlists

{% code title="$ ls -l /usr/share/wordlists" %}
```bash
dirb -> /usr/share/dirb/wordlists
dirbuster -> /usr/share/dirbuster/wordlists
fasttrack.txt -> /usr/share/set/src/fasttrack/wordlist.txt
fern-wifi -> /usr/share/fern-wifi-cracker/extras/wordlists
metasploit -> /usr/share/metasploit-framework/data/wordlists
nmap.lst -> /usr/share/nmap/nselib/data/passwords.lst
rockyou.txt.gz
wfuzz -> /usr/share/wfuzz/wordlist
```
{% endcode %}

## SecLists

{% embed url="https://github.com/danielmiessler/SecLists" %}

```bash
sudo apt install seclists
```

{% code title="$ ls -1 /usr/share/seclists" %}
```bash
Discovery/
Fuzzing/
IOCs/
Miscellaneous/
Passwords/
Pattern-Matching/
Payloads/
README.md
Usernames/
Web-Shells/
```
{% endcode %}

