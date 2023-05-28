16. Power of & - Get Matched Pattern

When & is used in the replacement-string, it replaces it with  
whatever text matched the original-string or the regular-expression.

Enclose the employee id between [ and ]:  
`sed 's/^[0-9][0-9][0-9]/[&]/g' employee.txt`

Enclose the whole input line between < and >:  
`sed 's/^.*$/<&>/' employee.txt`
