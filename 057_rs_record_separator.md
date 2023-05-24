# 57. RS - Record Separator

Assume you have the following text file which contains employee ids and names in a single line.  
`101,John Doe:102,Jason Smith:103,Raj Reddy:104,AnandRam:105,Jane Miller`

The default record separator used by awk is new line, so the following will not work as expected.  
`awk -F '{ print $2 }' employee-one-line.txt`  
=> *John Doe:102*

Specify the record separator to colon to treat this as 5 different line.  
`awk -F 'BEGIN { RS=":" } { print $2 }' employee-one-line.txt`

---

Assume you have the folloiwng text where records are separatord by a "-" on its own line.  
And all fields are one a separate line.
```
101
John Doe
CEO
-
102
Jason Smith
IT Manager
-
103
Raj Reddy
Sysadmin
-
104
Anand Ram
Developer
-
105
Jane Miller
Sales Manager
```

`awk 'BEGIN { FS="\n"; RS="-\n"; OFS=":" } { print $2, $3 }' employee-change-fs-rs-ofs.txt`
