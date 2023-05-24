# 70. If Else Statement

## Syntax:
```
if (conditional-expression)
    action1
else
    action2
```

## Ternary Operator Syntax:
`conditional-expression ? action1 : action2 ;`

The following example displays different message according to total quantity.
```
cat if-else.awk
BEGIN {
    FS=",";
}
{
    if ( $5 <= 5 )
        print "Buy More: Order", $2, "immediately!"
    else
        print "Sell More: Give discount on", $2, "immediately!"
}

awk -f if-else.awk items.txt
```

The following example uses the ternary operator to concatenate every 2lines from the items.txt file.  
`awk 'ORS=NR%2 ? "#" : "\n"' items.txt`

