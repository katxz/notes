# Linux Concepts

## Bash Environment

`bash` is a shell that allows us to run complex commands and perform different task from a terminal windows. It incorporates useful features from both the korn shell and the c shell.

{% embed url="https://apple.stackexchange.com/questions/361870/what-are-the-practical-differences-between-bash-and-zsh" %}

The behaviour of interactive shells in bash is determined by the system wide `bashrc` file located at `/etc/bash.bashrc`.

The system wide bash settings can be overridden by editing the `.bashrc` file located in any user's home directory. The `.bashrc` script is executed anytime that user logs in.

## Environment Variables

When opening a terminal window, a new bash process which has its own environment variables is initialised. These variables are a form of global storage for various settings inherited by any applications that are run during that terminal session. 

```text
env
printenv
```

{% embed url="https://askubuntu.com/questions/953579/what-is-the-difference-between-env-declare-and-compgen-v" %}

```text
echo $PATH
```

The `export` command makes the variable accessible to any subprocesses that might be spawn from the current bash instance.

```text
export var="test var"
bash
echo $var
```

If an environment variable is set without `export`, it will only be available from the current shell.

```text
var="test var"
bash
echo $var
```

### $$

{% code title="Displays the process ID of the current shell instance" %}
```text
echo $$
```
{% endcode %}

### $?

{% code title="Print out the return code" %}
```text
ping -c 1 10.11.1.5; echo $?
```
{% endcode %}

## **Piping and Redirection**

_\[ceebs writing notes for this\]_

