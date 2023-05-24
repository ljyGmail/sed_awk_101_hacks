# 66. Assignment Operators

![assignment operators](images/assignment_operators_1)
![assignment operators](images/assignment_operators_2)

The following example shows how to use assignment operations:
```
cat assignment.awk
BEGIN {
    FS=",";
    OFS=",";
    total1 = total2 = total3 = total4 = total5 = 10;
    total1 += 5; print total1;
    total2 -= 5; print total2;
    total3 *= 5; print total3;
    total4 /= 5; print total4;
    total5 %= 5; print total5;
}

awk -f assignment.awk
```

The following example uses the += shortcut assignment operator.  
`awk -F ',' 'BEGIN { total=0 } { total+=$5 } END { print "Total Quantity: " total }' items.txt`

The following example counts the total number of fields in a file.  
`awk -F ',' 'BEGIN { total=0 } { total += NF } END { print total }' items.txt`
