# 26. Sed as an Interpreter

To execute sed scripts from command line directly, add "#!/bin/sed -f" as the first line of the script file.
```
vim myscript.sed
#!/bin/sed -f
# Swap field 1 (employee id) with field 2 (employee name)
s/\([^,]*\),\([^,]*\),\(.*\).*/\2,\1,\3/g
# Enclose the whole line within < and >
s/^.*/<&>/
# Replace Developer with IT Manager
s/Developer/IT Manager/
# Replace Manager with Director
s/Manager/Director/
```

Now make the script executable and invoke it from the command line:
```
chmod u+x myscript.sed

./myscript.sed employee.txt
```

-n option can also be specified to suppress output.
```
vim testscript.sed
#!/bin/sed -nf
/root/ p
/nobody/ p

chmod u+x testscript.sed

./testscript.sed /etc/passwd
```

**Note** that the order of the options must be -nf (not -fn), or you'll get the following error message:
```
./testscript.sed /etc/passwd
/bin/sed: couldn't open file n: No such file or directory
```


