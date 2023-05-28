# 14. Sed Substitution Delimiter

```
vi path.txt
reading /usr/local/bin directory
```

Change /usr/local/bin to /usr/bin using substitute command:  
`sed 's/\/usr\/local\/bin/\/usr\/bin/' path.txt`

Ugly! Substitution delimiter can be any character. For example, | or ^ or @ or !:  
```
sed 's|/usr/local/bin|/usr/bin|' path.txt
sed 's^/usr/local/bin^/usr/bin^' path.txt
sed 's@/usr/local/bin@/usr/bin@' path.txt
sed 's!/usr/local/bin!/usr/bin!' path.txt
```
