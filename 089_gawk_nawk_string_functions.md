# 89. GAWK/NAWK String Functions

## Sub Function

Syntax:  
`sub(original-string, replacement-string, string-variable)`

- string-variable: This acts as both input and output string variable.

**Note**: sub function replaces only the first occurrence of the match.

```
cat sub.awk
BEGIN {
    state="CA is California";
    sub("C[Aa]", "KA", state);
    print state;
}

awk -f sub.awk
KA is California
```

The 3rd parameter string-variable is optional.  
When it is not specified, awk will use $0 (the current line).
```
awk '{ sub("10", "20"); print $0; }' items.txt
```

When a successful substitution happens, the sub function returns 1, otherwise it returns 0.

Print the record only when a successful substitution occurs:
```
awk '{ if (sub("HD", "High-Def")) print $0; }' items.txt
101,High-Def Camcorder,Video,210,10
```

## Gsub Function

gsub stands for global substitution.

In the following example, both "CA" and "Ca" are changed to "KA":
```
cat gsub.awk
BEGIN {
    state="CA is California";
    gsub("C[Aa]", "KA", state);
    print state;
}

awk -f gsub.awk
KA is KAlifornia
```

As with sub, the 3rd parameter is optional.

The following example replaces all occurrences of "10" in the line with "20":
```
awk '{ gsub("10", "20"); print $0; }' items.txt
201,HD Camcorder,Video,220,20
202,Refrigerator,Appliance,850,2
203,MP3 Player,Audio,270,15
204,Tennis Racket,Sports,190,20
205,Laser Printer,Office,475,5
```

## Match Function and RSTART, RLENGTH variables

Match function seaches for a given string, and returns a positive value when a successful match occurs.

Syntax:  
`match(input-string, search-string)`

The following example searches for "Cali" in the state string variable.
```
cat match.awk
BEGIN {
    state="CA is California";
    if (match(state, "Cali"))
    {
        print substr(state, RSTART, RLENGTH), "is present in:", state;
    }
}

awk -f match.awk
Cali is present in: CA is California
```

Match sets the following two special variables.  
- RSTART: the starting location of the search-string.
- RLENGTH: the length of the search-string.

