# 24. Sed Script Files

Create a sed script file with all the sed commands to execute a set of set commands.   
Using -f to execute it.

```
vim mycommands.sed
s/\([^,]*\),\([^,]*\),\(.*\).*/\2,\1,\3/g
s/^.*$/<&>/
s/Developer/IT Manager/
s/Manager/Director/

sed -f mycommands.sed employee.txt
<John Doe,101,CEO>
<Jason Smith,102,IT Director>
<Raj Reddy,103,Sysadmin>
<Anand Ram,104,IT Director>
<Jane Miller,105,Sales Director>
```
