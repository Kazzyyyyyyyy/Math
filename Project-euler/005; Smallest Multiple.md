```
# python 

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

### Explanation (math) 

**You can solve that problem purely through math - **

$n=$ the final number were looking for
$i=$ the number we are currently looking for 
$k=$ holds all the prime factors needed to get to $n$

Find the prime factors that are needed to form $i$ and add them to $k$, if $i$ cannot already be made with the existing prime factors in $k$ 


**- example -**

$i=2$: $k = 2$
$i=3$: $k = 2 * 3$
$i=4$: $k = 2 * 3 * 2$
$i=5$: $k = 2*3*2*5$
$i=6$: $k = 2*3*2*5$ - now we skip on adding a number, because we already have $2*3=6$ 
$i=7$: $k = 2*3*2*5*7$
$i=8$: $k = 2*3*2*5*7*2$ - multiplication is NOT limited to two factors, because we have $2*2=4$ we just add another $2$ to fullfill $i=8$ 


**- result -**

$k=2*3*2*5*7*2=840$
$n=840$ which is evenly divisible by all numbers ranging from 1 to 8. 
