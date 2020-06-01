# psexec.py \(Impacket\)

Source code: [https://github.com/SecureAuthCorp/impacket/blob/master/examples/psexec.py](https://github.com/SecureAuthCorp/impacket/blob/master/examples/psexec.py)

For how it works under the hood, see:

{% page-ref page="../kits/authenticated-rce/psexec.md" %}

## Usage

```text
psexec.py [[domain/]username[:password]@]<targetName or address>
```

Use `-hashes LMHASH:NTHASH` instead of specifying a password to authenticate using the **pass-the-hash** technique.

For more options, see source code.

