### My solution(s)

```
def valid(n): 
    for i in range(1, 20): 
        if n % i != 0:
            return False
        
    return True 


n = 2 
while True:
    if valid(n):
        break

    n += 1
```

```
check = [20, 19, 18, 17, 16, 14, 13, 11] # only check the biggest number of every prime in 2 - 20, because everything that is divisible by 20, is also divisible by 2, 5... 
 
def valid(n): 
    for i in check: 
        if n % i != 0:
            return False
        
    return True 


n = 2 
while True:
    if valid(n):
        break

    n += 1
```


### Explanation (math) 

$n=$ the final number were looking for
$i=$ the number we are currently looking for 
$k=$ holds all the prime factors needed to get to $n$

Find the prime factors that are needed to form $i$ and add them to $k$, if $i$ cannot already be made with the existing prime factors in $k$ 

$i=2$: $k = 2$
$i=3$: $k = 2 * 3$
$i=4$: $k = 2 * 3 * 2$
$i=5$: $k = 2*3*2*5$
$i=6$: $k = 2*3*2*5$ - now we skip on adding a number, because we already have $2*3=6$ 
$i=7$: $k = 2*3*2*5*7$
$i=8$: $k = 2*3*2*5*7*2$ - multiplication is NOT limited to two factors, because we have $2*2=4$ we just add another $2$ to fullfill $i=8$ 

$k=2*3*2*5*7*2=840$
$n=840$ which is evenly divisible by all numbers ranging from 1 to 8. 


### Explanation (algorithm)

```
k = 8 # range from 1 - k that n need to be divisible through
p = get_primes(k) # all primes from 2 - k 
n = 1 # result number

for prime in p: 
	exp = math.floor(math.log(k, prime))
    n *= prime ** exp
```


For each `prime`, we calculate the highest power, that is still $<=k$ through using: `floor(math.log(k, prime))`

If $prime=2$, the exponent is $3$; $2^3$ covers $2$, $4$ and $8$. 

For primes that are bigger than $8$ if squared, the exponent is $1$, which means they just get multiplied with `n`. 


#### optimization

```
k = 8 # range from 1 - k that n need to be divisible through 
p = get_primes(k) # all primes from 2 - k 
n = 1 # result number
limit = math.sqrt(k)

for prime in p: 
    exp = 1 # default exponent

    if prime <= limit: 
        exp = math.floor(math.log(k, prime))
    
    n *= prime ** exp 
```

We can optimize this algorithm very simply, through adding an upper limit for which primes the exponent must be included in the calculation. 
This limit is $\sqrt{k}$ because every prime bigger than that, is bigger than `k` itself when squared. 

