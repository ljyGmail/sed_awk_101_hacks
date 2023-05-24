# 60. FILENAME - Current File Name

FILENAME is helpful when multiple input-files are specified.  
`awk '{ print FILENAME }' employee.txt employee-multiple-fs.txt`

When read values from standard input, FILENAME will be set to "-".
```
awk '{ print "Last name:", $2; \
print "Filename:", FILENAME }'
John Doe
Last name: Doe
Filename: -
```

When piping the input to awk from another program, FILENAME will also be set to "-".  
`echo "John Doe" | awk '{ print "Last name:", $2; print "Filename:", FILENAME }'`

**Note:** FILENAME inside the BEGIN block will return empty value "",  
as BEGIN is for the whole awk program, not for any specific file.
