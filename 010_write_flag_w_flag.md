# 10. Write Flag (w flag)

Write only the lines that were changed by substitute command to output file:  
`sed -n 's/John/Johnny/w output.txt' employee.txt`

Change the 2nd instance of "locate" to "find", write the result to a file, print all lines:  
`sed 's/locate/find/2w output.txt' substitute-locate.txt`
