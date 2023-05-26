# 5. Write Pattern Space to File (w command)

Write the content of employee.txt to the file output.txt (and display on screen):  
`sed 'w output.txt' employee.txt`

Write the content of employee.txt to the file output.txt but not to screen:  
`sed -n 'w output.txt' employee.txt`

Write only the 2nd line:  
`sed -n '2 w output.txt' employee.txt`

Write lines 1 through 4:  
`sed -n '1,4 w output.txt' employee.txt`

Write from line 2 through the last line:  
`sed -n '2,$ w output.txt' employee.txt`

Write only add numbered lines:  
`sed -n '1~2 w output.txt' employee.txt`

Write lines matching the pattern "Jane":  
`sed -n '/Jane/ w output.txt' employee.txt`

Write lines starting from the first match of "Jason" until the 4th line:  
`sed -n '/Jason/,4 w output.txt' employee.txt`
**Note**: If there are no matches for "Jason" in the first 4 lines,  
this command writes only the lines that match "Jason" after the 4th line.

Write lines starting from the first match of "Raj" until the last line:  
`sed -n '/Raj/,$ w output.txt' employee.txt`

Write lines starting from the line matching "Raj" until the line matching "Jane":  
`sed -n '/Raj/,/Jane/ w output.txt' employee.txt`

Write the line matching "Jason" and the next 2 lines immediately after that:  
`sed -n '/Jason/,+2 w output.txt' employee.txt`

Instead of w command, output redirection is used more often.  
`sed 'p' employee.txt > output.txt`
