# 88. Generic String Functions

## Index Function

If the given string is not present, it will return 0, the index starts from 1.
```
cat index.awk
BEGIN {
    state="CA is California";
    print "String CA starts at location", index(state, "CA");
    print "String Cali starts at location", index(state, "Cali");

    if (index(state, "NY") == 0)
    {
        print "String NY is not found in:", state;
    }
}

awk -f index.awk
String CA starts at location 1
String Cali starts at location 7
String NY is not found in: CA is California
```

## Length Function

```
awk '{ print length($0) }' items.txt
29
32
27
31
30
```

## Split Function

Syntax:  
`split(input-string, output-array, separator)`

For this example, the original items-sold.txt is slightly changed to have different field delimiters.

```
cat items-sold1.txt
101:2,10,5,8,10,12
102:0,1,4,3,0,2
103:10,6,11,20,5,13
104:2,3,4,0,6,5
105:10,2,5,7,12,6

cat split.awk
BEGIN {
    FS=":";
}
{
    split($2, quantity, ",");
    total=0;
    for (x in quantity)
    {
        total += quantity[x];
    }
    print "Item", $1, ":", total, "quantities sold";
}

awk -f split.awk items-sold1.txt
```

## Substr Function

Syntax:  
`substr(input-string, location, length)`

The following example starts extracting the string from 5th character and prints the rest of the line.
```
awk '{ print substr($0, 5) }' items.txt
HD Camcorder,Video,210,10
Refrigerator,Appliance,850,2
MP3 Player,Audio,270,15
Tennis Racket,Sports,190,20
Laser Printer,Office,475,5
```

Start from the first character of the 2nd field and prints 5 characters:
```
awk -F"," '{ print substr($2, 1, 5) }' items.txt
HD Ca
Refri
MP3 P
Tenni
Laser
```
