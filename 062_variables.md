# 62. Variables

Awk variables don't need to be declared. If you wish to initialize an awk variable,  
it is better to do it in the BEGIN section, which will be executed only once.

There are no data types in Awk. Whether an awk variable is a number of a string  
depends on the context in which the variable is used in.

employee-sal.txt sample file  
`employee-number,employee-name,employee-title,salary`

The following examples shows how to create and use variables inside an awk script.
```
cat total-company-salary.awk
BEGIN {
    FS=",";
    total=0;
}
{
    print $2 "'s salary is: " $4;
    total+=$4;
}
END {
    print "---\nTotal company salary = $" total;
}

awk -f total-company-salary.awk employee-sal.txt
```
