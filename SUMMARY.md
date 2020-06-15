# Table of contents

* [Home](README.md)

## Methodology

* [Overview](methodology/overview.md)
* [Kits](kits-1/README.md)
  * [Code Snippets](kits-1/python.md)
  * [Tools](kits-1/tools-1/README.md)
    * [ufw](kits-1/tools-1/ufw.md)
    * [sshuttle](kits-1/tools-1/sshuttle.md)
    * [smbclient](kits-1/tools-1/smbclient.md)
    * [psexec.py \(Impacket\)](kits-1/tools-1/psexec.py-impacket.md)
    * [odat](kits-1/tools-1/odat.md)
    * [Nmap](kits-1/tools-1/nmap/README.md)
      * [NSE](kits-1/tools-1/nmap/nse.md)
      * [XML to HTML](kits-1/tools-1/nmap/xml-to-html.md)
    * [mssqlclient.py \(Impacket\)](kits-1/tools-1/mssqlclient.py-impacket.md)
    * [Metasploit](kits-1/tools-1/metasploit/README.md)
      * [exploit/multi/handler](kits-1/tools-1/metasploit/exploit-multi-handler.md)
      * [admin/oracle/oracle\_login](kits-1/tools-1/metasploit/admin-oracle-oracle_login.md)
    * [Burp](kits-1/tools-1/burp.md)
    * [Autorecon](kits-1/tools-1/autorecon.md)
  * [Useful Commands](kits-1/useful-windows-commands/README.md)
    * [Windows Commands](kits-1/useful-windows-commands/windows-commands.md)
    * [Linux Commands](kits-1/useful-windows-commands/linux-commands.md)

## Enumeration <a id="enumeraion"></a>

* [Overview](enumeraion/enumeration/README.md)
  * [Port Scanning](enumeraion/enumeration/port-scanning.md)
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
* [Port Redirection / Tunneling](enumeraion/tools.md)

## Collections

* [Authenticated RCE](collections/authenticated-rce.md)
* [Brute Force](collections/brute-force-cheat-sheet.md)
* [File Transfer](collections/file-transfer.md)
* [Path Traversal](collections/path-traversal-lists.md)
* [Reverse Shell](collections/reverse-shell/README.md)
  * [Reverse Shell Cheat Sheets](collections/reverse-shell/reverse-shell-cheat-sheets.md)
  * [Upgrade Shell](collections/reverse-shell/upgrade-shell.md)
  * [Powershell](collections/reverse-shell/shell-powershell.md)
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

## Exploit Development <a id="exploitation"></a>

* [Tools](exploitation/tools.md)
* [Buffer Overflow](exploitation/buffer-overflow.md)
* [Reversing](exploitation/reversing.md)

## Privilege Escalation

* [Manual Privesc Cheat Sheets](privilege-escalation/manual-privesc-cheat-sheets.md)
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

## Post Exploitation <a id="looting"></a>

* [Persistence](looting/persistence/README.md)
  * [Add New Admin User](looting/persistence/new-user.md)
* [Looting](looting/looting/README.md)
  * [mimikatz.exe](looting/looting/mimikatz.exe.md)
  * [SAM / SYSTEM / SECURITY](looting/looting/sam-system-security.md)
  * [passwd / shadow](looting/looting/passwd-shadow.md)
  * [Password Cracking](looting/looting/password-cracking.md)

## Kits

