# 23. Multiple Sed Commands in Command Line

## 1. Use multiple -e option in the command line
`sed -e 'command1' -e 'command2' -e 'command3' input-file`

Search for root or nobody or mail in the /etc/passwd file:  
`sed -n -e '/^root/ p' -e '/^nobody/ p' -e '/^mail/ p' /etc/passwd`

## 2. Break-up several sed commands using \
```
sed -n -e '/^root/ p' \
-e '/^nobody/ p' \
-e '/^mail/ p' \
/etc/passwd
```
## 3. Group multiple commands using {}
```
sed -n '{
/^root/ p
/^nobody/ p
/^mail/ p
}' /etc/passwd
```
