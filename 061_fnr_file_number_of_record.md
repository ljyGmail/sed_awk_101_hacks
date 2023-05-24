# 61. FNR - File "Number of Record"

When multiple input files are specified, NR will not be reset to 1 after one file is processed.
```
awk 'BEGIN { FS="," } \
{ print FILENAME ": record number", NR, "is" , $1 } \
END { print "Total number of records:", NR }' \
employee.txt employee-multiple-fs.txt
```

FNR will output record number within the current file.
```
awk 'BEGIN { FS="," } \
{ print FILENAME ": record number", FNR, "is", $1; } \
END { print "Total number of records:", NR }' \
employee.txt employee-multiple-fs.txt
```

The following example shows both NR and FNR:
```
vim fnr.awk

BEGIN {
    FS=","
}
{
    printf "FILENAME=%s NR=%s FNR=%s\n", FILENAME, NR, FNR;
}
END {
    printf "END Block: NR=%s FNR=%s\n", NR, FNR
}

awk -f fnr.awk employee.txt employee-multiple-fs.txt
```
