# 81. Multi Dimensional Array

Awk has only **one dimensional** array.  
But a multi dimensional array can be simulated using single dimensional array.

In the following script, even "1,1" has been specified as index, it is not two indexes.
```
cat array-multi.awk
BEGIN {
    item["1,1"]=10;
    item["1,2"]=20;
    item["2,1"]=30;
    item["2,2"]=40;

    for (x in item)
    {
        print item[x];
    }
}

awk -f array-multi.awk
```

The next script uses index withou quotes. Awk uses a subscript separator with default value of "\034".  
When writing item[1,2], it will be translated to item["1\0342"].  
But when writing item["1,2"], it will not be translated.
```
cat array-multi2.awk
BEGIN {
    item[1,1]=10;
    item[1,2]=20;
    item[2,1]=30;
    item[2,2]=40;

    for (x in item)
    {
        print item[x];
    }
}

awk -f array-multi2.awk
```

In the following script, indices with and without quotes are mixed.
```
cat array-multi3.awk
BEGIN {
    item["1,1"]=10;
    item["1,2"]=20;
    item[2,1]=30;
    item[2,2]=40;

    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
}

awk -f array-multi3.awk
```
