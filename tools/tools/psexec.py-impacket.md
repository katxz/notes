# psexec.py (Impacket)

Source code: [https://github.com/SecureAuthCorp/impacket/blob/master/examples/psexec.py](https://github.com/SecureAuthCorp/impacket/blob/master/examples/psexec.py)

For how it works under the hood, see:

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## Usage

```
psexec.py [[domain/]username[:password]@]<targetName or address>
```

Use `-hashes LMHASH:NTHASH` instead of specifying a password to authenticate using the **pass-the-hash** technique.

For more options, see source code.
