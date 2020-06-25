# Linux Common Commands

See the not so commonly used commands in the next page:

{% page-ref page="linux-useful-utilities.md" %}

## history

`Ctrl`+`R` 

```text
history -c
```

### !

```text
!30
!!
```

### Environment variables

```text
export HISTCONTROL=ignoredups
export HISTIGNORE="l[als]:[bf]g:exit:history"
export HISTTIMEFORMAT='%F %T '
export HISTSIZE=10000
export HISTFILESIZE=20000
```

For more `HISTTIMEFORMAT` options, run `man strftime`

## alias

```text
alias  // list all defined aliases
alias mkdir='ping -c 1 localhost'
unalias mkdir
```

## apt \| dpkg

```text
sudo apt update
sudo apt upgrade

apt-cache search pure-ftpd
apt list | less
apt list gobuster
apt show resource-agents | less

sudo apt install pure-ftpd
sudo apt remove --purge pure-ftpd
```

`dpkg` is the core tool used to install a package either directly or indirectly through `apt`.

It is also the preferred tool to use when operating offline since it does not require Internet connection.

Note that `dpkg` will not install any dependencies a package might require. 

```text
sudo dpkg -i ./package.deb
```

## service \| systemctl

{% embed url="https://askubuntu.com/questions/903354/difference-between-systemctl-and-service-commands" %}

```text
sudo systemctl start apache2
sudo systemctl enable apache2
systemctl status openvas-scanner.service
systemctl list-unit-files
```

## man \| apropos

### man

```text
man -k passwd
man -k '^passwd$'
man 5 passwd
```

### apropos

Can search the list of man page descriptions for a possible match based on a keyword. Often helpful to find a particular command based on a description

```text
apropos partition
```

## mkdir \| cp \(a list of dir / files\)

```text
mkdir -p test/{recon,exploit,report}
```

```text
cp /usr/share/exploitdb/exploits/windows/remote/{643.c,646.c} .
```

## date

`-d, --date=STRING` display time described by STRING, not 'now'

`-u, --utc, --universal` print or set Coordinated Universal Time \(UTC\)

```text
date
Wed 24 Jul 2019 01:58:53 PM AEST

date -u -d @1563554177
Fri 19 Jul 2019 04:36:17 PM UTC
```

## which \| locate \| find

### which

`which` command search through directories defined in the $PATH environment variable for a given file name. $PATH is a colon separated list of directory paths that bash will search through whenever a command is run without a full path.

```text
which python
```

### locate

`locate` command searches a built-in database called `locate.db`. It is automatically updated by a cron scheduler or can be updated manually

```text
sudo updatedb
locate python
```

### find

`find` can search for files and directories by more than just the name. Can search by file age, size, owner, file type, timestamp, permissions and more.

```text
sudo find / -name sdb*
```

## tr \| grep \| sed \| cut \| awk \| sort \| uniq \| wc

### tr

`tr` translate or delete characters.

`-d --delete` delete characters in SET1, do not translate.

```text
printf $(cat fake-payload.txt | tr -d '\n') 
```

### grep

`-r` recursive searching 

`-i` ignore case

In addition, the variant programs `egrep`, `fgrep` and `rgrep` are the same as grep -E, grep -F, and grep -r, respectively. These variants are deprecated, but are provided for backward compatibility.

```text
ls -la /usr/bin | grep zip
grep keyword file.txt
grep -o 'regex'
grep -oE 'extended regex'
grep -v invertmatchkeyword file.txt
```

### sed

`sed` performs text editing on a stream of text --- either a set of specific files or stdout.

```text
echo "I need to try hard" | sed 's/hard/harder/'
```

### cut

The `cut` command is used to extract a section of text from a line and output it to the standard output. 

`-d` is a field delimiter and it only accepts a single character

```text
cut -d ":" -f 1 /etc/passwd
```

### awk

`awk` is a programming language designed for text processing, and is typically used as a data extraction and reporting tool.

`-F` is the field separator flag \(the default separator is `tab`\)

```text
echo "hello::there::friend" | awk -f "::" '{print $1, $3}'
```

### sort

`-u` unique

`-r` reverse sort

`-n` numeric sort

```text
sort -urn
```

### uniq

The `-c` option of uniq will prefix the output line with the number of occurrences.

```text
uniq -c
```

### wc

print newline, word, and byte counts for each file

`-c, --bytes`

`-m, --chars`

`-l, --lines`

`-w, --words`

```text
wc file.txt
cat file.txt | wc -l
wc -m < file.txt
```

## comm \| diff \| vimdiff

### comm

The `comm` command compares two text files, displaying the lines that are unique to each one, as well as the lines they have in common. 

It outputs three space-offset columns: 

* the first contains lines that are unique to the first file or argument; 
* the second contains lines that are unique to the second file or argument; and 
* the third column contains lines that are shared by both files. 
* The `-n` switch, where `n` is either 1, 2, or 3, can be used to suppress one or more columns, depending on the need.

```text
comm scan-a.txt scan-b.txt
```

![](../../.gitbook/assets/image%20%281%29.png)

```text
comm -12 scan-a.txt scan-b.txt
```

### diff

The `diff` command is used to detect differences between files, similar to the comm command.

Two of the most popular formats include the context format \(-c\) and the unified format \(-u\).

```text
diff -c scan-a.txt scan-b.txt
```

![](../../.gitbook/assets/image%20%283%29.png)

```text
diff -u scan-a.txt scan-b.txt
```

![](../../.gitbook/assets/image%20%284%29.png)

### vimdiff

`vimdiff` shortcuts:

* `[` + `C`
* `]` + `C`
* `D` + `O`
* `D` + `P`

## **t**ar \| gunzip

### tar

```text
tar xvzf file.tar.gz
tar cvzf file.tar.gz /file/location/path/
```

### gunzip

```text
gunzip access_log.txt.gz
```

## ss \| netstat

### ss

```text
sudo ss -antup
sudo ss -ntulp
```

### netstat

```text
sudo netstat -antup
sudo netstat -ntulp
```

## ping

```text
ping -c 1 10.11.1.5
```

## ifconfig \| ip

```text
ifconfig tun0
```

```text
ip a
```

## & \| bg \| fg \| jobs \| ps \| kill

### Backgrounding Processes

* &
* `Ctrl` + `Z` to suspend a started job. Once it has been suspended, run `bg` command to resume it in the background

Keep in mind that some processes are time sensitive and may give incorrect results if left suspended too long.

### **Job Control**

The built-in `jobs` utility lists all the jobs that are running in the current terminal session. 

* Running `fg %<job number>` returns the job to the foreground.
* Or `kill %<job number>` terminates the suspended job.

![](../../.gitbook/assets/image%20%285%29.png)

There are various ways to refer to a job in the shell. The “%” character followed by a JobID represents a job specification. The JobID can be a process ID \(PID\) number or you can use one of the following symbol combinations:

* %Number : Refers to a job number such as `%1` or `%2`
* %String : Refers to the beginning of the suspended command’s name such as %commandName, e.g. `%ping`
* `%+` OR `%%` : Refers to the current job
* `%-` : Refers to the previous job

Note that if only one process has been backgrounded, the job number is not needed.

### **Process Status \(ps\)**

`-e` select all processes.

`-f` do full-format listing.

```text
ps -ef
```

`-C` select by command name

```text
ps -fC leafpad
```

`a` and `x` flags to list all processes with or without a tty

`u` flag to list the processes in a user-readable format

```text
ps aux
```

`-o format` user-defined format

`-U --User userlist`  select by real user ID \(RUID\) or name

```text
ps -o pid,ppid,pgid,gid,sess,cmd -U root
```

### Terminate Processes \(kill\)

Kill a group of processes with their PGID \(Process Group ID\)

```text
kill -9 -$PGID
```

## tail \| watch

### tail

`-f` follow

`-n2` last 2 lines instead of default 10

```text
tail -f file.txt
tail -n2 file.txt
```

### watch

The `watch` command is used to run a designated command at regular intervals. 

By default, it runs every two seconds but we can specify a different interval by using the -n X option to have it run every “X” number of seconds. 

For example, this command will list logged-in users \(via the w command\) once every 5 seconds

```text
watch -n 5 w
```

Use `Ctrl` + `C` to return to the interactive terminal.

## wget \| curl \| axel

### wget

```text
wget -O report.pdf <url>
```

### curl

```text
curl -o report.pdf <url>
```

### axel

`axel` is a download accelerator that transfers a file from a FTP or HTTP server through multiple connections. `axel` speeds up downloads extremely well and is especially useful for large downloads.

`-n`, is used to specify the number of multiple connections to use 

`-a`, option for a more concise progress indicator

`-o`, to specify a different file name for the downloaded file

```text
axel -a -n 20 -o report.pdf
```

