# 18. Substitution Grouping (Multiple Group)

Get only the first column (emp id) and the 3rd column (title):  
sed 's/\([^,]\),\([^,]\),\([^,]\).*/\1,\3/g'

Swap field 1 (emp id) with field 2 (emp name):  
sed 's/\([^,]\),\([^,]\),\([^,]\).*/\2,\1,\3/g'
