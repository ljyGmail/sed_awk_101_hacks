## 22. Sed Substitution Using Regular Expression

Replace the last two characters in every line of employee.txt with ",Not Defined":
```
sed 's/..$/,Not Defined/' employee.txt
101,John Doe,C,Not Defined
102,Jason Smith,IT Manag,Not Defined
103,Raj Reddy,Sysadm,Not Defined
104,Anand Ram,Develop,Not Defined
105,Jane Miller,Sales Manag,Not Defined
```

Delete the result of the line starting from "Manager":
```
sed 's/Manager.*//' employee.txt
101,John Doe,CEO
102,Jason Smith,IT
103,Raj Reddy,Sysadmin
104,Anand Ram,Developer
105,Jane Miller,Sales
```

Delete all lines that start with "#":
`sed -e 's/#.*//; /^$/ d' employee.txt`

Create the folliwing test.html for the next example:
```
vim test.html
<html><body><h1>Hello World!</h1></body></html>
```

Strip all html tags from test.html:
```
sed -e 's/<[^>]*>//g' test.html
Hello World!
```

Remove all comments and blank lines:  
`sed -e 's/#.*//' -e '/^ *$/ d' /etc/profile`

Remove only the comments. Leave the blank lines:  
`sed -e '/^#.*/ d' /etc/profile`

Convert the DOS file format to Unix file format using sed:  
`sed 's/.$//' filename`
