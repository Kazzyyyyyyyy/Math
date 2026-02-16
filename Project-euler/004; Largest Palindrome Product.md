```
# python 

def is_palindrome(x): 
    n = x 
    rev = 0

    while n > 0:         
        rev = rev * 10 + n % 10 
        n //= 10

    return x == rev


x = 999
largest = 0
while x > 99:  
    y = x
    while y > 99: 
        if is_palindrome(y * x): 
            if y*x > largest: 
                largest = y * x
            else: 
                break 
        
        y -= 1
    x -= 1

```

