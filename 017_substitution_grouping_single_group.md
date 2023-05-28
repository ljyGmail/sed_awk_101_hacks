# 17. Substitution Grouping (Single Group)

Single grouping (priting only employee id):  
`sed 's/\([^,]*\).*/\1/g' employee.txt`

Print only the first field(username) from the /etc/passwd file:  
`sed 's/\([^:]*\).*/\1/' /etc/passwd`

The following script encloses the first letter in every word inside ():  
`echo "The Geek Stuff" | sed 's/\(\b[A-Z]\)/\(\1\)/g'`

```
vim numbers.txt
1
12
123
1234
12345
123456
```

Commify numbers, i.e. insert commas to make them more readable:  
`sed 's/\(^|[^0-9.]\)\([0-9]\+\)\([0-9]\{3\}\)/g' numbers.txt`
