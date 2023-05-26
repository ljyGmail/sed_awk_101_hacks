# 4. Delete Lines (d command)

By default, if no address range before the d command is specified, all the lines are matched.  
The following script will not print anything.  
`sed 'd' employee.txt`

Specify an adress range to be deleted.

Delete only the 2nd line:  
`sed '2 d' employee.txt`

Delete from line 1 through 4:  
`sed '1,4 d' employee.txt`

Delete from line 2 through the last line:  
`sed '2,$ d' employee.txt`

Delete only odd numbered lines:  
`sed '1~2 d' employee.txt`

Delete lines matching the patter "Manager":  
`sed '/Manager/ d' employee.txt`

Delete lines starting from the first match of "Jason" until the 4th line:  
`sed '/Jason/,4 d' employee.txt`  
**Note**: if there are no matches for "Jason" in the first 4 lines,  
this command will delete lines that match "Jason" after the 4th line. 

Delete lines starting from the first match of "Raj" until the last line:  
`sed '/Raj/,$ d' employee.txt`

Delete lines starting from the line matching "Raj" until the line matching "Jane":  
`sed '/Raj/,/Jane/ d' employee.txt`

Delete lines starting from the line matching "Jason" and 2 lines immediately after that:  
`sed '/Jason/,+2 d' employee.txt`

## Useful Delete Examples

Delete all the empty lines from a file:  
`sed '/^$/ d' employee.txt`

Delete all comment lines (assuming the comment starts with #):  
`sed '/^#/ d' employee.txt`
