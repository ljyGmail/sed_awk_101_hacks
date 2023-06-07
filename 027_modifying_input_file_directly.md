# 27. Modifying the Input File Directly

To make a modification directly on the input-file, redirect the output to a temporary file,  
and then rename the temporary file to a new file.
```
sed 's/John/Johnny/' employee.txt > new-employee.txt
mv new-employee.txt employee.txt
```

Or use option -d to modify the input file directly.
```
sed -i 's/John/Johnny/' employee.txt

$ cat employee.txt
101,Johnny Doe,CEO
102,Jason Smith,IT Manager
103,Raj Reddy,Sysadmin
104,Anand Ram,Developer
105,Jane Miller,Sales Manager
```

Replace John with Johnny in the original file but save a backup copy:  
```
sed -i.bak 's/John/Johnny/' employee.txt
sed --in-place=.bak 's/John/Johnny/' employee.txt
```

