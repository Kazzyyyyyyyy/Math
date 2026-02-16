
```
# python

def primes(num): 
    l = [True] * num 
    l[0] = l[1] = False # 0*0 = 0 & 1 != prime
    
    for (i, isPrime) in enumerate(l):
        if isPrime: 
            yield i 
            for j in range(i*i, num, i): 
                l[j] = False 
```

