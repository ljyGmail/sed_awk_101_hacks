# 59. NR - Number of Records

NR is very helpful. When used inside the body, it gives the current line number.  
When used in the END block, it gives the total number of records in the file.

The following statement shows how NR works in the body and END block.  
`awk 'BEGIN { FS="," } { print "Emp Id of record number", NR, "is", $1 } \  
END { print "Total number of records:", NR }' employee.txt`
