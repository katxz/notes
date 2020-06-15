# WebDav

## WebDav Credentials

Relevant links:

* [https://www.digitalocean.com/community/tutorials/how-to-configure-webdav-access-with-apache-on-ubuntu-12-04](https://www.digitalocean.com/community/tutorials/how-to-configure-webdav-access-with-apache-on-ubuntu-12-04)

Apache webdav is commonly configured under `/etc/apache2/sites-enabled/000-default`, for example:

```text
Alias /webdav /var/www/webdav

<Location /var/www/webdav>
    Options Indexes
    DAV On
    AuthType Basic
    AuthName "webdav"
    AuthUserFile /etc/apache2/webdav.password
    Require valid-user
</Location>
```

The `webdav.password` file can be cracked, or even better, just **add more users** to **access** the **webdav** server:

```bash
htpasswd /etc/apache2/users.password <USERNAME> #You will be prompted for the password
```

To check if the new credentials are working, can just visit the page, or use `wget`:

```bash
wget --user <USERNAME> --ask-password http://domain/path/to/webdav/ -O - -q
```

Or can use `cadaver`:

```bash
$ cadaver http://localhost/webdav/
Authentication required for webdav on server `localhost':
Username: test
Password:
dav:/webdav/> quit
Connection to `localhost' closed.
```

