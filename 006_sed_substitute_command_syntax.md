# 6. Sed Substitute Command Syntax

`sed '[address-range|pattern-range] s/original-string/replacement-string/[substitute-flags]' input-file`

Replace all of first occurrence on each line of Manager with Director:  
`sed 's/Manager/Director/' employee.txt`

Replace Manager with Director only on lines that contain the word 'Sales':  
`sed '/Sales/ s/Manager/Director/' employee.txt`
