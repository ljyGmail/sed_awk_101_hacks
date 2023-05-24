# 58. ORS - Output Record Separator

The following statement adds a new line with "---" after each and every line that is printed.  
`awk 'BEGIN { FS=","; ORS="\n---\n" } { print $2, $3 }' employee.txt`

The following statement prints every field on its own line, separating each record with a "---" line.  
`awk 'BEGIN { FS=","; OFS="\n"; ORS="\n---\n" } { print $1, $2, $3 }' employee.txt`
