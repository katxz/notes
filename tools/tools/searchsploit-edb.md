# Searchsploit (EDB)

```
$ man searchsploit

$ searchsploit -t ms17-010 --exclude="(PoC)|(Metasploit)" -w

$ searchsploit samba
$ searchsploit samba --exclude="(PoC)|/dos/"
$ searchsploit -x 643  # open file
$ searchsploit -p 643  # get path


$ searchsploit afd windows -w -t
$ searchsploit "afd windows" -w -t

$ searchsploit -t "Samba 2.2.*"  # search the exploit title (better search method)
$ searchsploit -w  # return the URL for exploit-db.com rather than the local path
$ searchsploit "dirty cow"  # dirty cow is great

# My aliases
$ ss samba
$ ssx 643
$ ssp 643

$ cd /usr/share/exploitdb/exploits
```
