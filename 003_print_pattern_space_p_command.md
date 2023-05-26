# 3. Print Pattern Space (p command)

Using the sed p command can print the current pattern space.

Usually p command is used with -n option to suppress the default printing behavior,  
and to specify which lines to print.

The following script prints every line twice.  
`sed 'p' employee.txt`

Print each line once (functionally the same as **cat** command)  
`sed -n 'p' employee.txt`

## Specifying an Address Range

Print only the 2nd line:  
`sed -n '2 p' employee.txt`

Print from line 1 through line 4:  
`sed -n '1,4 p' employee.txt`

Print from line 2 through the last line ($ represents the last line):  
`sed -n '2,$ p' employee.txt`

## Modify Address Range

Address range can be modified using comma, plus, and tilde.

- Comma(,) is used to specify address range.
- Plus(+) may be used in conjunction with the comma, to specify a number of lines instead of an absolute line number.
- Tilde(~) is to skip lines between commands. n~m means sed should start at the nth line and pick up every mth line.

Print only odd numbered lines:  
`sed -n '1~2 p' employee.txt`

## Pattern Matching

Print lines matching the pattern "Jane":  
`sed -n '/Jane/ p' employee.txt`

Print lines starting from the 1st match of "Jason" until the 4th line:  
`sed -n '/Jason/,4 p' employee.txt`  
**Note**: If there were no match for "Jason", the command would print lines that match "Jason" after the 4th line.

Print lines starting from the first match of "Raj" until the last line:  
`sed -n '/Raj/,$ p' employee.txt`

Print lines starting from the line matching "Raj" until the line matching "Jane":  
`sed -n '/Raj/,/Jane/ p' employee.txt`

Print the lines matching "Jason" and 2 lines immediately after that:  
`sed -n '/Jason/,+2 p' employee.txt`
