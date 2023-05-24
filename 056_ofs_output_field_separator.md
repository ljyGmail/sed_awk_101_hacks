# 56. OFS - Output Field Separator

By default, awk prints the output fields with space between the field.  
`awk -F ',' '{ print $2, $3 }' employee.txt`

The following statement print three values containing space in between them.  
`awk -F ',' '{ print $2, ":", $3 }' employee.txt`

The default output field separator can be modified by setting the value of OFS.  
`awk -F ',' 'BEGIN { OFS=":" } { print $2, $3 } employee.txt`

When spcifying a comma in the pring statement between different print values, awk will use the OFS.  
`awk 'BEGIN { print "test1", "test2" }'`

When not separate values with a comma in the print statement, awk will print the values with nothing in between.  
`awk 'BEGIN { print "test1" "test2" }'`
