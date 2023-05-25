# 79. Browse the Array using the For Loop

## Syntax:
```
for (index in arrayname)
    actions
```

The following script uses for loop to loop through all the elements in an array.
```
cat array-for-loop.awk
BEGIN {
    item[101]="HD Camcorder";
    item[102]="Refrigerator";
    item[103]="MP3 Player";
    item[104]="Tennis Racket";
    item[105]="Laser Printer";
    item[1001]="Tennis Ball";
    item[55]="Laptop";
    item["na"]="Not Available";
    
    for (x in item)
    {
        print item[x];
    }
}
```
