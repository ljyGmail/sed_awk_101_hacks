# 86. Built-in Numeric Functions

## Awk int(n) Function

Int Function Example:
```
awk 'BEGIN {
    print int(3.534);
    print int(4);
    print int(-5.223);
    print int(-5);
}'

3
4
-5
-5
```

## Awk log(n) Function

Log Function Example:
```
awk 'BEGIN {
    print log(12);
    print log(0);
    print log(1);
    print log(-1);
}'

2.48491
-inf
0
nan
```

## Awk sqrt(n) Function

Sqrt Function Example:
```
awk 'BEGIN {
    print sqrt(16);
    print sqrt(0);
    print sqrt(-12);
}'

4
0
nan
```

## Awk exp(n) Function

Exp Function Example:
```
awk 'BEGIN {
    print exp(123434346);
    print exp(0);
    print exp(-12);
}'

inf 1 6.14421e-06
```

## Awk sin(n) Function

Sine Function Example:
```
awk 'BEGIN {
    print sin(90);
    print sin(45);
}'

0.893997
0.850904
```
## Awk cos(n) Function

Cosine Function Example:
```
awk 'BEGIN {
    print cos(90);
    print cos(45);
}'

-0.448074
0.525322
```

## Awk atan2(m, n) Function

Atan2 Function Example:
```
awk 'BEGIN { print atan2(30, 45) }'

0.588003
```
