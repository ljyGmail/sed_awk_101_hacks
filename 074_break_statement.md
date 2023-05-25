# 74. Break Statement

The following example prints any item number that has a month with no sold items.
```
cat break.awk
{
    i=2; total=0;
    while(i++ <= NF)
    {
        if($i == 0)
        {
            print "Item", $1, "had a month with no items sold";
            break;
        }
    }
}

awk -f break.awk items-sold.txt
```

A loop that is executed exactly 10 times and is terminated by a break statement.
```
awk 'BEGIN {
    x=1;
    while (1)
    {
        print "Iteration";
        if (x == 10)
        {
            break;
        }
        x++;
    }
}'
```
