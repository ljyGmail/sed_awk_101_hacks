# 19. Gnu Sed Only Replacement String Flags

## \l replacement string flag
\l replaces the character that immediately follows it as lower case.

Change John to JOhNNY:  
`sed -n 's/John/JO\lHNNY/p' employee.txt`

## \L replacement string flag
\L treats the rest of the characters as lower case.

Change Johnny to JOhnny:  
`sed -n 's/John/JO\LHNNY/p' employee.txt`

## \u replacement string flag
\u replaces the character that immediately follows it as upper case.

Change John to joHnny:  
`sed -n 's/John/jo\uhnny/p' employee.txt`

## \U replacement string flag
\U treats the rest of the characters as upper case.

Change John to joHNNY:  
`sed -n 's/John/jo\Uhnny/p' employee.txt`

## \E replacement string flag
\E stops the conversion initiated by either \L or \U.

Change John to JOHNNY BOY:  
`sed -n 's/John/\UJohnny Boy/p' employee.txt`

Change John to JOHNNY Boy:  
`sed -n 's/John/\UJohnny\E Boy/p' employee.txt`

## Replacement String Flags Usages
The replacement string flags are useful when combined with grouping.

Emoloyee name in all upper case, and title in all lower case:  
`sed 's/\([^,]*\),\([^,]*\),\(.*\).*/\U\2\E,\1,\L\3/g' employee.txt`
