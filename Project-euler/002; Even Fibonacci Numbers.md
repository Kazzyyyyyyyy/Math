
```
# python

maxVal = 4_000_000 
tail = 1 
head = 2 
sum = 2 

while head < maxVal: 
    next = tail + head
    tail = head 
    head = next 

    if next % 2 == 0: 
        sum += next

print(sum)
```


