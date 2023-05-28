12. Execute Flag (e flag)

```
cat files.txt
/etc/passwd
/etc/group
```

Add the text "ls -l " in front of every line in the files.txt and print the output:  
`sed 's/^/ls -l /' files.txt`

Add the text "ls -l " in front of every line in the files.txt and execute the output:  
`sed 's/^/ls -l /e' files.txt`
