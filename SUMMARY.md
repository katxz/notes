# Table of contents

* [Home](README.md)

## Methodology

* [Overview](methodology/overview.md)
* [Kits](kits/README.md)
  * [Code Snippets](kits/code-snippets.md)
  * [Tools](kits/tools/README.md)
    * [ufw](kits/tools/ufw.md)
    * [sshuttle](kits/tools/sshuttle.md)
    * [smbclient](kits/tools/smbclient.md)
    * [psexec.py \(Impacket\)](kits/tools/psexec.py-impacket.md)
    * [odat](kits/tools/odat.md)
    * [Nmap](kits/tools/nmap/README.md)
      * [NSE](kits/tools/nmap/nse.md)
      * [XML to HTML](kits/tools/nmap/xml-to-html.md)
    * [mssqlclient.py \(Impacket\)](kits/tools/mssqlclient.py-impacket.md)
    * [Metasploit](kits/tools/metasploit/README.md)
      * [exploit/multi/handler](kits/tools/metasploit/exploit-multi-handler.md)
      * [admin/oracle/oracle\_login](kits/tools/metasploit/admin-oracle-oracle_login.md)
    * [Burp](kits/tools/burp.md)
    * [Autorecon](kits/tools/autorecon.md)
  * [Useful Commands](kits/useful-windows-commands/README.md)
    * [Windows Commands](kits/useful-windows-commands/windows-commands.md)
    * [Linux Commands](kits/useful-windows-commands/linux-commands.md)

## Enumeration <a id="enumeraion"></a>

* [Overview](enumeraion/overview/README.md)
  * [Port Scanning](enumeraion/overview/port-scanning.md)
* [Ports](enumeraion/ports/README.md)
  * [21 - FTP](enumeraion/ports/21-ftp.md)
  * [22 - SSH](enumeraion/ports/22-ssh/README.md)
    * [Debian OpenSSL Predictable PRNG \(CVE-2008-0166\)](enumeraion/ports/22-ssh/debian-openssl-predictable-prng-cve-2008-0166.md)
  * [25 - SMTP](enumeraion/ports/25-smtp.md)
  * [53 - DNS](enumeraion/ports/53-dns.md)
  * [80 \| 443 - HTTP\(S\)](enumeraion/ports/80-or-443-http-s.md)
  * [113 - ident](enumeraion/ports/113-ident.md)
  * [139 \| 445 - SMB](enumeraion/ports/139-or-445-smb.md)
  * [222 - rsh](enumeraion/ports/222-rsh.md)
  * [1433 - MSSQL](enumeraion/ports/1433-mssql.md)
  * [1521 - Oracle](enumeraion/ports/1521-oracle.md)
  * [2049 - NFS](enumeraion/ports/2049-nfs.md)
  * [3306 - MySQL / MariaDB](enumeraion/ports/3306-mysql-mariadb.md)
  * [3389 - RDP](enumeraion/ports/3389-rdp.md)
  * [5985 \| 5986 - WINRM](enumeraion/ports/5985-or-5986-winrm.md)
  * [U:69 - TFTP](enumeraion/ports/u-69-tftp.md)
* [Port Redirection / Tunneling](enumeraion/port-redirection-tunneling.md)

## Collections

* [Authenticated RCE](collections/authenticated-rce.md)
* [Brute Force](collections/brute-force.md)
* [File Transfer](collections/file-transfer.md)
* [Path Traversal](collections/path-traversal.md)
* [Reverse Shell](collections/reverse-shell/README.md)
  * [Reverse Shell Cheat Sheets](collections/reverse-shell/reverse-shell-cheat-sheets.md)
  * [Upgrade Shell](collections/reverse-shell/upgrade-shell.md)
  * [Powershell](collections/reverse-shell/powershell.md)
  * [PHP](collections/reverse-shell/php.md)
  * [IIS / ASP](collections/reverse-shell/iis-asp.md)
  * [Perl / CGI](collections/reverse-shell/perl-cgi.md)
  * [JSP](collections/reverse-shell/jsp.md)
  * [Python](collections/reverse-shell/python.md)
  * [Meterpreter](collections/reverse-shell/meterpreter.md)
* [Web Attacks](collections/web-attacks/README.md)
  * [NoSQL Injection](collections/web-attacks/nosql-injection.md)
  * [WebDav](collections/web-attacks/webdav.md)
* [Wordlists](collections/wordlists.md)

## Exploit Development

* [Tools](exploit-development/tools.md)
* [Buffer Overflow](exploit-development/buffer-overflow.md)
* [Reversing](exploit-development/reversing.md)

## Privilege Escalation

* [Manual Privesc](privilege-escalation/manual-privesc.md)
* [History Files](privilege-escalation/history-files.md)
* [Windows Privilege Escalation](privilege-escalation/windows-privilege-escalation/README.md)
  * [Scripts](privilege-escalation/windows-privilege-escalation/scripts.md)
  * [Token Manipulation](privilege-escalation/windows-privilege-escalation/token-manipulation.md)
  * [Unquoted Service Paths](privilege-escalation/windows-privilege-escalation/unquoted-service-paths.md)
  * [JuicyPotato](privilege-escalation/windows-privilege-escalation/juicypotato.md)
  * [RogueWinRM](privilege-escalation/windows-privilege-escalation/roguewinrm.md)
* [Linux Privilege Escalation](privilege-escalation/linux-privilege-escalation/README.md)
  * [Uncommon SUID Files](privilege-escalation/linux-privilege-escalation/uncommon-suid-files.md)
  * [sudoedit](privilege-escalation/linux-privilege-escalation/sudoedit.md)

## Post Exploitation

* [Persistence](post-exploitation/persistence/README.md)
  * [Add New Admin User](post-exploitation/persistence/add-new-admin-user.md)
* [Looting](post-exploitation/looting/README.md)
  * [mimikatz.exe](post-exploitation/looting/mimikatz.exe.md)
  * [SAM / SYSTEM / SECURITY](post-exploitation/looting/sam-system-security.md)
  * [passwd / shadow](post-exploitation/looting/passwd-shadow.md)
  * [Password Cracking](post-exploitation/looting/password-cracking.md)

