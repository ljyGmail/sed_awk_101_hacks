# 92. OFMT

When a number is converted to a string for printing,  
awk uses OFMT format to decide how to print the values.  
The default value is "%.6g".

When using g, count all the characters on both sides of the dot.  
When using f, count **ONLY** the characters on the right side of the dot.

The following example shows how the output will be printed using various OFMT values.
```
vim ofmt.awk
BEGIN {
    total=143.123456789;
    print "----using g----";
    print "Default OFMT:", total;
    OFMT="%.3g";
    print "%.3g OFMT", total;
    OFMT="%.4g";
    print "%.4g OFMT", total;
    OFMT="%.5g";
    print "%.5g OFMT", total;
    OFMT="%.6g";
    print "%.6g OFMT", total;
    print "----using f----";
    OFMT="%.0f";
    print "%.0f OFMT:", total;
    OFMT="%.1f";
    print "%.1f OFMT:", total;
    OFMT="%.2f";
    print "%.2f OFMT:", total;
    OFMT="%.3f";
    print "%.3f OFMT:", total;
}

awk -f ofmt.awk
---using g----
Default OFMT: 143.123
%.3g OFMT: 143
%.4g OFMT: 143.1
%.5g OFMT: 143.12
%.6g OFMT: 143.123
---using f----
%.0f OFMT: 143
%.1f OFMT: 143.1
%.2f OFMT: 143.12
%.3f OFMT: 143.123
```
