# JuicyPotato

Good reference:

* [https://ohpe.it/juicy-potato/](https://ohpe.it/juicy-potato/)
* [https://book.hacktricks.xyz/windows/windows-local-privilege-escalation/juicypotato](https://book.hacktricks.xyz/windows/windows-local-privilege-escalation/juicypotato)

## CLSID Problems

If you can't find **any working CLSID** you should visit this page:

{% embed url="https://ohpe.it/juicy-potato/CLSID/" %}

There you can **find** some **CLSID that you could** use instead of the default one to privesc.

**You could also try to find other working CLSID.**

### **Checking CLSIDs**

First, you will need some executables apart from juicypotato.exe.

Download [Join-Object.ps1](https://github.com/ohpe/juicy-potato/blob/master/CLSID/utils/Join-Object.ps1) and load it into your PS session, and download and execute [GetCLSID.ps1](https://github.com/ohpe/juicy-potato/blob/master/CLSID/GetCLSID.ps1). That script will create a list of possible CLSIDs to test.

Then download [test\_clsid.bat ](https://github.com/ohpe/juicy-potato/blob/master/Test/test_clsid.bat)\(change the path to the CLSID list and to the juicypotato executable\) and execute it. It will start trying every CLSID, and **when the port number changes, it will mean that the CLSID worked**.

**Check** the working CLSIDs **using the parameter -c**

