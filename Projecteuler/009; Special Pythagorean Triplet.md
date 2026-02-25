### My solution(s)

```
def solve(n): 
    for c in range(2, n): 
        for b in range(2, c): 
            for a in range(2, b): 
                if (b*b + a*a) == c*c and a + b + c == n: 
                    return a * b * c
n = 1000 
```