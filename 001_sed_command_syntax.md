# 1. Sed Command Syntax

## Basic sed syntax
`sed [options] {sed-commands} {input-file}`

The following script prints all the lines from the /etc/passwd file.  
`sed -n 'p' /etc/passwd`

## Basic sed syntax for use with sed-command file:
`sed [options] -f {sed-commands-in-a-file} {input-file}`

The following script prints lines beginning with root and nobody from /etc/passwd. 
```
vim test-script.sed
/^root/ p
/^nobody/ p

sed -n -f test-script.sed /etc/passwd
```

## Base sed syntax for executing multiple sed commands using -e option:  
`sed [options] -e {sed-command-1} -e {sed-command-2} {input-file}`

The following script prints lines beginning with root and nobody from /etc/passwd.
`sed -n -e '/^root/ p' -e '/^nobody/ p' /etc/passwd`

One sed command that is to long can be split into multiple lines using a backslash.
```
sed -n \
-e '/^root/ p' \
-e '/^nobody/ p' \
/etc/passwd
```

Multiple sed commands in the command line can be grouped together by usng {}.

## Basic sed syntax using {}:
```
sed [options] '{
sed-command-1
sed-command-1
}' input-file
```

The following script demonstrates this version of basic syntax.
```
sed -n '{
/^root/ p
/^nobody/ p
}' /etc/passwd
```
