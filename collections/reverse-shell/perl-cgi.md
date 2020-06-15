# Perl / CGI

CGI scripts are essentially perl script. So if discovered LFI in a web server that executes _.cgi_ scripts. 

* Upload or serve a perl reverse shell \(`/usr/share/webshells/perl/perl-reverse-shell.pl`\), 
* Change the extension from .pl to .cgi
* Update permissions \(`chmod +x`\)
* Access the reverse shell from the web browser to execute it.

