# 73. For Loop Statement

## Syntax:
```
for (initialization; condition; increment/decrement)
    actions
```

The following example prints the sum of fields in a line.
```
echo "1, 2, 3, 4" | awk \
'{ for (i = 1; i <= NF; i++) total += $i; }; \
END { print total }'
```

The following example prints all the fields in the reverse order.
```
cat forreverse.awk
BEGIN {
    ORS="";
}
{
    for (i = NF; i > 0; i--)
        print $i, " ";
    print "\n";
}

awk -f forreverse.awk items-sold.txt
```

For-loop version of the program to print the total quantity sold for each item.
```
cat for.awk
{
    total=0;
    for (i=2; i <= NF; i++)
        total += $i;
    print "Item", $1, ":", total, "quantities sold";
}

awk -f for.awk items-sold.txt
```
