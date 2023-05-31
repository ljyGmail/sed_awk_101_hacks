# 91. Argument Processing (ARGC, ARGV, ARGIND)

The following script shows how ARGC, ARGV behave:
```
cat arguments.awk
BEGIN {
    print "ARGC=", ARGC;
    for (i=0; i < ARGC; i++)
    {
        print ARGV[i]
    }
}

awk -f arguments.awk arg1 arg2 arg3 arg4 arg5
ARGC= 6
awk
arg1
arg2
arg3
arg4
arg5
```

The following script passes some arguments and set value according to argument values.
```
cat argc-argv.awk
BEGIN {
    FS=",";
    OFS=",";
    for (i=0; i < ARGC; i++)
    {
        if (ARGC[i] == "--item")
        {
            itemnumber = ARGV[i+1];
            delete ARGV[i];
            i++;
            delete ARGV[i];
        }
        else if
        {
            quantity = ARGV[i+1];
            delete ARGV[i];
            i++;
            delete ARGV[i];
        }
    }
}
{
    if ($1 == itemnumber)
        print $1, $2, $3, $4, quantity;
    else
        print $0;
}

awk -f argc-argv.awk --item 104 --qty 25 items.txt
101,HD Camcorder,Video,210,10
102,Refrigerator,Appliance,850,2
103,MP3 Player,Audio,270,15
104,Tennis Racket,Sports,190,25
105,Laser Printer,Office,475,5
```

In gawk the file that is currently getting processed is stored in the ARGV array  
that is accessed from the **body** loop.  
The ARGIND is the index to this ARGV array to retrieve the current file.

```
cat argind.awk
{
    print "ARGIND:", ARGIND;
    print "Current file:", ARGV[ARGIND];
}

awk -f argind.awk items.txt items-sold.txt
ARGIND: 1
Current file: items.txt
ARGIND: 1
Current file: items.txt
ARGIND: 1
Current file: items.txt
ARGIND: 1
Current file: items.txt
ARGIND: 1
Current file: items.txt
ARGIND: 2
Current file: items-sold.txt
ARGIND: 2
Current file: items-sold.txt
ARGIND: 2
Current file: items-sold.txt
ARGIND: 2
Current file: items-sold.txt
ARGIND: 2
Current file: items-sold.txt
```
