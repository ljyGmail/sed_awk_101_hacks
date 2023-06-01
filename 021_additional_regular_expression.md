# 21. Additional Regular Expressions

## OR Operation (|)

Print lines containing either 101 or 102:
```
sed -n '/101\|102/ p' employee.txt
101,John Doe,CEO
102,Jason Smith,IT Manager
```

Print lines that contain a character from 2 to 3 or contain string 105:
```
sed -n '/[2-3\|105]/ p' employee.txt
101,John Doe,CEO
102,Jason Smith,IT Manager
```

**Note** that the **|** symbol is escaped with a **/**.

Print lines that contain a character from 2 to 3 or that contain the string 105:
```
sed -n '/[2-3]\|105/ p' employee.txt
102,Jason Smith,IT Manager
103,Raj Reddy,Sysadmin
105,Jane Miller,Sales Manager
```

## Exactly M Occurrences ({m})

For this example create the following numbers.txt file.
```
vim numbers.txt
1
12
123
1234
12345
123456
```

Print lines that contain any digit (will print all lines):
```
sed -n '/[0-9]/ p' numbers.txt
1
12
123
1234
12345
123456
```

Print lines consisting of exactly 5 digits:
```
sed -n '/^[0-9]\{5\}$/ p' numbers.txt
12345
```

## M to N Occurrences ({m,n})

Print lines consisting of at least 3 but not more than 5 digits:
```
sed -n '/^[0-9]\{3,5\}/ p' numbers.txt
123
1234
12345
```

## Word Boundary (\b)

Create the following sample file for testing.
```
cat words.txt
word matching using: the
word matching using: thethe
word matching using: they
```

Match lines containing the whole word "the":
```
sed -n '/\bthe\b/ p' words.txt
word matching using: the
```

Match lines containing words that start with "the":
```
sed -n '/\bthe/ p' words.txt
word matching using: the
word matching using: thethe
word matching using: they
```

## Back References (\n)

Match only the line that has the word "the" repeated twice:
```
sed -n '/\(the\)\1/ p' words.txt
word matching using: thethe
```
