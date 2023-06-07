# 93. GAWK Built-in Environment Variables

## ENVIRON

*ENVIRON* is an array that contains all the environment values.
```
cat environ.awk
BEGIN {
    OFS="=";
    for ( x in ENVIRON )
    {
        print x, ENVIRON[x];
    }
}

awk -f environ.awk
```

## IGNORECASE

By default, awk programs are case sensitive.

`awk '/video/ { print }' items.txt`

Set IGNORECASE to 1 to make it case insensitive.
```
awk 'BEGIN { IGNORECASE = 1; } /video/ { print }' items.txt
101,HD Camcorder,Video,210,10
```

In the following script, we can see that IGNORECASE works for both string and regular expression comparisons:
```
cat ignorecase.awk
BEGIN {
    FS=",";
    IGNORECASE=1;
}
{
    if ($3 == "video") print $0;
    if ($2 ~ "TENNIS") print $0;
}

awk -f ignorecase.awk items.txt
101,HD Camcorder,Video,210,10
104,Tennis Racket,Sports,190,20
```

## ERRNO

When there is an error while using I/O opertions,  
the ERRNO variable will contain the corresponding error message .

```
vim errno.awk
{
    print $0;
    x = getline < "dummy-file.txt";
    if ( x == -1 )
        print ERRNO;
    else
        print $0;
}

awk -f error.awk items.txt
101,HD Camcorder,Video,210,10
No such file or directory
102,Refrigerator,Appliance,850,2
No such file or directory
103,MP3 Player,Audio,270,15
No such file or directory
104,Tennis Racket,Sports,190,20
No such file or directory
105,Laser Printer,Office,475,5
No such file or directory
```

