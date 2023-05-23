# 53. Print Command

By default, print command without any argument prints the whole line.  
`awk '{print}' employee.txt`

Print specific fields in a record by passing $field-number as a print command argument.  
`awk '{print $2}' employee.txt`

Specify field delimiter.  
`awk -F ',' '{print $2}' employee.txt`

When there is only one character used for delimiter, any of the following forms works.  
```
awk -F ',' '{print $2}' employee.txt
awk -F "," '{print $2}' employee.txt
awk -F, '{print $2}' employee.txt
```  

A simple report that prints employee name and title with a header and footer.
```
awk -F ',' 'BEGIN \
{ print "-------------\nName\tTitle\n-------------"} \
{ print $2, "\t", $3;} \
END { print "-------------"; }' employee.txt
```

$0 represents the whole record. Both of the following commands are the same.
```
awk '{print}' employee.txt
awk '{print $0}' employee.txt
```
