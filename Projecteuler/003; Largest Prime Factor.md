
```
# python 

n = 600851475143
factor = 2 
lastFactor = 1 

while n > 1:
    if n % factor == 0:           # factor perfectly divides n
        lastFactor = factor       # save current prime factor 
        n /= factor               # remove factor from n

        while n % factor == 0:    # remove all occurences of factor in n
            n /= factor

    factor += 1                   # find prime that perfectly divides n
```



### Explanation 

Every factor found is guaranteed to be prime because we test from smallest to largest - composite numbers (like 4, 6, 8) can never divide ```n```, since their prime factors (2, 3) were already removed earlier.


### Related

- [[Sieve Of Eratosthenes]]
- [[Prime's]]
