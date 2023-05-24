# 72. Do-While Loop

## Syntax:
```
do
action
while (condition)
```

The following example, the print statement is executed exactly once.
```
awk 'BEGIN {
count=1;
do
    print "This gets printed at least once";
while (count != 1)
}'
```

The following script prints the total number of quantities sold.
```
cat dowhile.awk
{
    i=2; total=0;
    do
    {
        total += $i;
        i++;
    } while (i <= NF)
    print "Item", $1, ":", total, "quantities sold";
}

awk -f dowhile.awk items-sold.txt
```
