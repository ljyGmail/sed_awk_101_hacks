# 82. SUBSEP - Subscript Separator

The default subscript separator can be changed to anything using the SUBSEP variable.
```
cat array-multi4.awk
BEGIN {
    SUBSEP=":";

    item["1,1"]=10;
    item["1,2"]=20;
    
    item[2,1]=30;
    item[2,2]=40;

    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
}

awk -f array-multi4.awk
```

For a multi-dimensional array, the best practice is not to enclose any of the indexes within quotes.
```
cat array-multi5.awk
BEGIN {
    SUBSEP=":";

    item[1,1]=10;
    item[1,2]=20;
    item[2,1]=30;
    item[2,2]=40;

    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
}

awk -f array-multi5.awk
```
