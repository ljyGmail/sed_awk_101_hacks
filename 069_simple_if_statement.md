# 69. Simple If Statement

## Single Action
```
if (conditional-expression)
    action
```

## Multiple Actions
```
if (conditional-expression)
{
    action1;
    action2;
}
```

Print all the items with quantity <= 5:
```
awk -F "," '{ if ($5 <= 5) \
print "Only", $5, "qty of", $2, "is available"; }' \
items.txt
```

Multiple conditional operators in an if statement.
```
awk -F "," \
'{ if ( ($4 >= 500 && $4 <= 1000) && ($5 <= 5)) \
print "Only", $5, "qty of", $2 "is avalable";}' items.txt
```
