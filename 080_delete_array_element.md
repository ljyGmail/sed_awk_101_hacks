# 80. Delete Array Element

## Syntax:
`delete arrayname[index];`

The loop command below removes all elements from an array.  
```
for (index in array)
    delete array[index]
```

In GAWK, the following single command deletes all the elements from an array.  
`delete array`

Also, as shown in the example below, item[103]="" does not delete the array element.  
It just stores null values in it.
```
cat array-delete.awk
BEGIN {
    item[101]="HD Camcorder";
    item[102]="Refrigerator";
    item[103]="MP3 Player";
    item[104]="Tennis Racket";
    item[105]="Laser Printer";
    item[1001]="Tennis Ball";
    item[55]="Laptop";
    item["na"]="Not Available";

    delete item[102];
    item[103]="";
    delete item[104];
    delete item[1001];
    delete item["na"];

    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
}

awk -f array-delete.awk
```
