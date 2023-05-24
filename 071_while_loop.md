# 71. While Loop

## Syntax:
```
while (condition)
    actions
```

The example below prints x 50 times.  
`awk 'BEGIN { while ( count++ < 50 ) string=string "x"; print string }'`

The following script prints the total number of items sold.
```
cat while.awk
{
    i=2; total=0;
    while (i <= NF)
    {
        total += $i;
        i++;
    }
    print "Item", $1, ":", total, "quantities sold";
}

awk -f while.awk items-sold.txt
```
