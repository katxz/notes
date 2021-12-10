# Linux Code Snippets

## Remove Windows carriage return character

Example error message: `/usr/bin/python^M: bad interpreter: No such file or directory`

```
sed -i -e 's/\r$//' file.sh
```

## **Convert binary to decimal**

```
echo "$((2#00011000))"
```

## **Decode base64**

```
echo "base64encodedstring" | base64 -d
```

## Convert unix timestamp

```
date -u -d @1563554177
```

\
