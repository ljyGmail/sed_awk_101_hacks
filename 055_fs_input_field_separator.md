# 55. FS - Input Field Separator

Field separator can be specified using -F option.  
`awk -F ',' '{print $2, $3}' employee.txt`

Field separator can also be specifed using the FS AWK built-in variable.  
Specify the FS in the BEGIN block as shown below.  
`awk 'BEGIN {FS=","} {print $2, $3}' employee.txt`

Multiple awk statements can be written in the BEGIN block.  
Multiple commands inside the BEGIN or END block are separated by semi-colon.
```
awk 'BEGIN { FS=","; \
print "-------------\nName\tTitle\n-------------" } \
{ print $2, "\t", $3; } \
END { print "-------------" }' employee.txt
```

Note that the default field separator is not just a single space.  
It actually matches one or more whitespace characters.

When a file contants different field separators, FS can be specified using regular expressions.
`awk 'BEGIN { FS="[,:%]" } { print $2, $3 }' employee-multiple-fs.txt`
