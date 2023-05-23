# 54. Pattern Matching

The following prints the names and titles of the Managers:  
`awk -F ',' '/Manager/ {print $2, $3}' employee.txt`

The following prints the employee name whose Emp id is 102:  
`awk -F ',' '/^102/ {print "Emp id 102 is", $2}' employee.txt`
