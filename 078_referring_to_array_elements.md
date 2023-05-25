# 78. Referring to Array Elements

If you refer to an array element that doesn't exist, awk will automatically  
create that array element with the given index, and ssign null value to it.

Check whether a particular array index exists in the array:  
`if ( index in array-name )`

The following is an array reference example:
```
cat array-refer.awk
BEGIN {
    x = item[55];
    if ( 55 in item )
    {
        print "Array index 55 contains", item[55];
    }

    item[101]="HD Camcorder";
    if ( 101 in item )
    {
        print "Array index 101 contains", item[101];
    }

    if ( 1010 in item )
    {
        print "Array index 1010 contains", item[1010];
    }
}

awk -f array-refer.awk
```

- item[55] is no assigned with any value earlier, but it is refered in "x = item[55]",  
so awk will automatically create this element with null value.
- item[101] is assigned a value, so it is present.
- item[1010] does not exist, so it is not present.
