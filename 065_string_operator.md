# 65. String Operator

(space) is a string operator that does string concatenation.

This operator is why you must separator the values in a print statement  
with a comma if you want to print the OFS in between.

```
cat string.awk
BEGIN {
    FS=",";
    OFS=",";
    string1="Audio";
    string2="Video";
    numberstring="100";
    string3=string1 string2;
    print "Concatenate string is:" string3;
    numberstring=numberstring+1;
    print "String to number:" numberstring;
}

awk -f string.awk items.txt
```
