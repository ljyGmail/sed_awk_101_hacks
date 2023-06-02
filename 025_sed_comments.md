# 25. Sed Comments

```
vim mycommands.sed
# Swap field 1 (employee id) with field 2 (employee name)
s/\([^,]*\),\([^,]*\),\(.*\).*/\2,\1,\3/g
# Enclose the whole line within < and >
s/^.*$/<&>/
# Replace Developer with IT Manager
s/Developer/IT Manager/
# Replace Manager with Director
s/Manager/Director/
```
