# 84. Sort Array Indexes using asorti

Just like sorting array values, array indexes can be sorted and stored in a new array using asorti.

The following scirpt shows how asorti differs from asort.  
- **asort** sorts the indexes and stores them as values of an array.
- If specify asorti(array), the original values will be lost.   
To be safe, always specify two parameter to the asorti function.
```
cat asorti.awk
BEGIN {
    state["TX"]= "Texas";
    state["PA"]= "Pennsylvania";
    state["NV"]= "Nevada";
    state["CA"]= "California";
    state["AL"]= "Alabama";

    print "----- Function: asort -----"
    total = asort(state, statedesc)
    for (i=1; i <= total; i++)
    {
        print "Index", i, "contains", statedesc[i];
    }

    print "----- Function: asorti -----"
    total = asorti(state, stateabbr);
    for (i=1; i <= total; i++)
    {
        print "Index", i, "contains", stateabbr[i];
    }
}
```
