# Linux Code Snippets

## Remove Windows carriage return character

Example error message: `/usr/bin/python^M: bad interpreter: No such file or directory`

```text
sed -i -e 's/\r$//' file.sh
```

## **Convert binary to decimal**

```text
echo "$((2#00011000))"
```

## **Decode base64**

```text
echo "base64encodedstring" | base64 -d
```

## Convert unix timestamp

```text
date -u -d @1563554177
```

  


