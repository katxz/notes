# Passive Information Gathering

## Frameworks and Tools

### OSINT Framework&#x20;

{% embed url="https://osintframework.com/" %}

### Maltego

{% embed url="https://www.paterva.com/buy/maltego-clients.php" %}

## User Information Gathering

### Email Harvesting

```
theHarvester -d megacorpone.com -b google
```

### Password Dumps

Examples:

* [https://en.wikipedia.org/wiki/RockYou#Data\_breach](https://en.wikipedia.org/wiki/RockYou#Data\_breach)
* [https://haveibeenpwned.com/PwnedWebsites](https://haveibeenpwned.com/PwnedWebsites)

### Social Media Tools

* Social-Searcher [https://www.social-searcher.com](https://www.social-searcher.com)
* Twofi [https://digi.ninja/projects/twofi.php](https://digi.ninja/projects/twofi.php)
* linkedin2username [https://github.com/initst ring/linkedin2username](https://github.com/initstring/linkedin2username)

### Stack Overflow

The site’s value from an information gathering perspective is in looking at the types of questions a given user is asking or answering. If we can reasonably determine a user on Stack Overflow is also an employee of our target organisation, we may be able to infer some things about the organisation based on the employee’s questions and answers.



## Website Recon

If the client has a website, we can gather basic information by simply browsing the site.

Find employee information, emails (and email address format) and social media accounts, etc.

## Whois

Whois is a TCP service, tool, and a type of database that can provide information about a domain such as and registrar.

* standard forward search by passing the domain name get registrar details and name servers
* reverse lookups gives information on who's hosting the IP address

## Google Hacking

{% embed url="https://www.exploit-db.com/google-hacking-database" %}
GHDB
{% endembed %}

{% code title="Examples" %}
```
filetype:php

site:example.com
site:example.com -filetype:html

intitle:"index of" "parent directory"

ext:jsp
ext:cfm
ext:pl
```
{% endcode %}

## Netcraft

{% embed url="https://www.netcraft.com/" %}

{% embed url="https://searchdns.netcraft.com" %}

## Recon-ng

```
kali@kali:~$ recon-ng
[recon-ng][default] > marketplace search github

[recon-ng][default] > marketplace info recon/domains-hosts/google_site_web
[recon-ng][default] > marketplace install recon/domains-hosts/google_site_web
[recon-ng][default] > modules load recon/domains-hosts/google_site_web
[recon-ng][default][google_site_web] > info
[recon-ng][default][google_site_web] > options set SOURCE megacorpone.com
[recon-ng][default][google_site_web] > run
[recon-ng][default][google_site_web] > back 

[recon-ng][default] > show
[recon-ng][default] > show hosts

[recon-ng][default] > marketplace info recon/hosts-hosts/resolve
[recon-ng][default] > marketplace install recon/hosts-hosts/resolve
[recon-ng][default] > modules load recon/hosts-hosts/resolve
[recon-ng][default][resolve] > info
[recon-ng][default][resolve] > run
[recon-ng][default][resolve] > show hosts
```

{% hint style="info" %}
An “Invalid command” error may indicate that we are at the wrong command level. If this happens, run back to return to the main recon-ng prompt and try the command again.
{% endhint %}

## Github

```
user:megacorpone filename:users
```

### Tools: Gitrob and Gitleaks

{% hint style="success" %}
Tools that search through source code for secrets, like Gitrob or Gitleaks, generally rely on regular expressions or entropy based detections to identify potentially useful information.&#x20;

Regular expressions are a predefined search pattern. They are particularly useful for searching through a body of text for variations of commonly used passwords.&#x20;

Entropy-based detection, on the other hand, attempts to find strings that are randomly generated. The idea here is that a long string of random characters and numbers is probably a password.&#x20;

Regardless of how a tool searches for secrets, no tool is perfect and they will miss things that a manual inspection might find.
{% endhint %}

## Shodan

{% embed url="https://www.shodan.io/" %}

```
hostname:megacorpone.com
```

## Security Headers Scanner

{% embed url="https://securityheaders.com/" %}

## SSL Server Test

{% embed url="https://www.ssllabs.com/ssltest/" %}

## Pastebin

{% embed url="https://pastebin.com/" %}

