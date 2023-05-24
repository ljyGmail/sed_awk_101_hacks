# 68. Regular Expression Operators

![regular expression operators](images/regular_expression_operators.png)

Print lines where field two is "Tennis":  
`awk -F "," '$2 == "Tennis"' items.txt`

Print lines where field two contains "Tennis":  
`awk -F "," '$2 ~ "Tennis"' items.txt`

Print lines where field two does not contain "Tennis":  
`awk -F "," '$2 !~ "Tennis"' items.txt`

The following example prints the total number of users who use /bin/bash as their shell.  
`awk -F ':' '$NF ~ /\/bin\/sh/ { n++ } END { print n }'` /etc/passwd
