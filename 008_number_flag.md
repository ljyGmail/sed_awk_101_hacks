# 8. Number Flag (1, 2, 3.. flag)

Use the number flag to specify a specific occurrence of the original-string.

Replace the 2nd occurrence of a to A:  
`sed 's/a/A/2' employee.txt`

For this example, create the following file with three lines:
```
$vim substitute-locate.txt
locate command is used to locate files
locate command uses database to locate files
locate command can also use regex for searching
```

Change only the 2nd occurrence of locate to find:  
`sed 's/locate/find/2' substitute-locate.txt`
