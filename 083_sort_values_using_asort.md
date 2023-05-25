# 83. Sort Array Values Using asort

The **asort** function sorts the array values and stores them in indexes from 1 through n.  
Where n is the total number of elements in the array.

In the following script, array indexes with various non-consecutive numbers and strings  
will be sorted based on values. After the asort, the array values will be sorted and  
stored in the indexes 1, 2, 3, 4... asort returns the total number of items in the array.
```
cat asort.awk
BEGIN {
    item[101]="HD Camcorder";
    item[102]="Refrigerator";
    item[103]="MP3 Player";
    item[104]="Tennis Racket";
    item[105]="Laser Printer";
    item[1001]="Tennis Ball";
    item[55]="Laptop";
    item["na"]="Not Available";
    
    print "------Before asort------"
    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
    total = asort(item);

    print "------After asort------"
    for (x in item)
    {
        print "Index", x, "contains", item[x];
    }
    print "Return value from asort:", total;
}
```

In the following example, the original array "item" is not modified.  
Istead, the "itemnew" array will contain the new indexes.  
`total = asort(item, itemnew)`
