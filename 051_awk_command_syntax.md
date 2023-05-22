# 51. Awk Command Syntax

## Basic Awk Syntax
awk -Fs '/pattern/ {action}' input-file
(or)
awk -Fs '{action}' input-file

`awk -F: '/mail/ {print $1}' /etc/passwd`

## Awk Commands in a Separate File

awk -Fs -f myscript.awk input-file

`awk -f myscript.awk input-file`
