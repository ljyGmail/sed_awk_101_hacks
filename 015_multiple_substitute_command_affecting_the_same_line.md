# 15. Multiple Substitute Commands Affecting the Same Line

Change Developer to IT Manager, the change Manager to Director:
```
sed '{
    s/Developer/IT Manager/
    s/Manager/Director/
} employee.txt
'
```
