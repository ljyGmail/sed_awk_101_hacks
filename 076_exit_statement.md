# 76. Exit Statement

The exit statement causes the script to immediately stop excuting the current commands,  
and also ignores the remaining lines from the input file.

The following awk script exits during the 5th iteration.
```
awk 'BEGIN {
    x=1;
    while (x <= 10)
    {
        if (x == 5)
        {
            exit;
        }
        print "Value of x", x;
        x++;
    }
}'
```

The following script prints the first item number that has a month with no items sold and stop running.
```
cat exit.awk
{
    i=2;
    while (i++ <= NF)
    {
        if ($i == 0)
        {
            print "Item", $1, "Had a month with no item sold.";
            exit;
        }
    }
}

awk -f exit.awk items-sold.txt
```
