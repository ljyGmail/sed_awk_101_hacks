# 87. Random Number Generator

## Awk rand() Function

The following example generates 1000 random numbers between 0 and 100, and show how often each number was generated.
```
cat rand.awk
BEGIN {
    while (i < 1000)
    {
        n = int(rand() * 100);
        rnd[n]++;
        i++;
    }

    for(i=0; i<=100; i++) 
    {
        print i, "occured", rnd[i], "times";
    }
}

awk -f rand.awk
```

## Awk srand(n) Function

Generate 5 random numbers starting from 5 to 50:
```
cat srand.awk
BEGIN {
    # Initialize the seed with 5.
    srand(5);

    # Totally I want to generate 5 numbers.
    total=5;

    # Maximum number is 50.
    max=50;
    count=0;

    while (count < total)
    {
        rnd = int(rand() * max);
        if ( arran[rnd] == 0)
        {
            count++;
            arran[rnd]++;
        }
    }

    for (i=5; i<=max; i++)
    {
        if ( array[i] )
        {
            print i;
        }
    }
}
```
