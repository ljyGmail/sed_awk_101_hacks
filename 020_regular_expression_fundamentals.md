# 20. Regular Expression Fundamentals

## Beginning of line (^)

Display lines which start with 103:  
`sed -n '/^103/ p' employee.txt`

## End of line ($)

Display lines which end with the letter r:  
`sed -n '/r$/ p' employee.txt`

## Single Character (.)

The following script will substitute the pattern "J followed by three characters and a space"  
with "Jason followed by a space".  
`sed -n 's/J... /Jason /p' employee.txt`

## Zero or more Occurrences (*)

For this example create the following *log.txt* file:
```
vim log.txt
log: Input Validated
log:
log:  testing resumed
log:
log:output created
```

Display all lines that contain "log:" followed by an optional space followed by a character:  
`sed -n '/log: *./p' log.txt`

## One or more Occurrences (\+)

Display all lines that contain "log:" followed by one or more spaces:  
`sed -n '/log: \+/ p' log.txt`

## Zero or one Occurrences (\?)

Display all lines that contain "log:":  
`sed -n '/log: \?/ p' log.txt`

## Escaping the Special Character (\)

Escapte dot:  
`sed -n '/127\.0\.0\.1/ p' /etc/passwd`

## Character Class ([0-9])

Match any line that contains 2 or 3 or 4:  
`sed -n '/[234]/ p' employee.txt`

Match any line that contains 2 or 3 or 4 (alternate form):  
`sed -n '/[2-4]/ p' employee.txt`
