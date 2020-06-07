# 25 - SMTP

## Connect with Telnet

```text
$ telnet $TARGET 25
Trying $TARGET...
Connected to $TARGET.
Escape character is '^]'.
220 mail.local ESMTP Postfix (Debian/GNU)

EHLO test.example.com
250-mail.local
250-PIPELINING
250-SIZE 10240000
250-VRFY
250-ETRN
250-STARTTLS
250-ENHANCEDSTATUSCODES
250-8BITMIME
250 DSN

VRFY notuser
550 5.1.1 <nouser>: Recipient address rejected: User unknown in local recipient table
VRFY user
252 2.0.0 user

MAIL FROM:<test@example.com>
RCPT TO:<user@mail.local>

DATA
Subject: Testmessage
(Blank line, press Enter again)
This is a test.
(Blank line, press Enter again)
.

QUIT
```

