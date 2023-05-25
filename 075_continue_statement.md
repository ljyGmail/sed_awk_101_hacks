# 75. Continue Statement

The following script prints the total number of quantites sold using continue statement.
```
cat continue.awk
{
    i=1; total=0;
    while (i++ < NF)
    {
        if (i == 1) continue;
        total += $i;
    }
    print "Item", $1, ":", total, "quantities sold";
}

awk -f continue.awk items-sold.txt
```

The following script prints the value of x at each iteration except 5.
```
awk 'BEGIN {
    x=1;
    while (x <= 10)
    {
        if (x == 5)
        {
            x++;
            continue;
        }
        print "Value of x", x;
        x++;
    }
}'
```
