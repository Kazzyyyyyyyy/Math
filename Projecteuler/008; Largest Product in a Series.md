### My solution(s)

```
#single time; 0.7896913749992381
#general time; 78969.13749992382
n = 7316717... # 1000 digit number
digits = 13 # length of adjecent digits we need to check 

def prod(head): 
    p = 1 
    for i in l[head-digits:head]:
        p *= i
    
    return p

def solve(): 
    biggestProd = 0 
    currProd = 1 

    for head in range(digits, len(l)): 
        currProd = prod(head)
        if currProd > biggestProd:
            biggestProd = currProd

    return biggestProd
```

```
n = 7316717... # 1000 digit number
l = [int(d) for d in str(n)] # turn integer n into an array

# single time; 0.23342763699940405
# general time; 23342.763699940406

def solve(): 
    digits = 13 # length of adjacent digits product has to be made of 
    biggestProd = 0
    currProd = 1 

    tail = 0 
    reset = 0

    for (head, num) in enumerate(l):
        if head >= digits: # skip division until currProd is made up of 13 digits 
            # divide out tail only if non-zero and window contains no zero
            if l[tail] > 0 and head >= reset + digits: 
                currProd //= l[tail]

            tail += 1

        if num > 0: 
            currProd *= num
        else: 
            currProd = 1 # set it to one instead of zero, because 0 * X == 0
            reset = head # block division until currProd contains no zero anymore

        if currProd > biggestProd: 
            biggestProd = currProd

    return biggestProd
```

```
//3654ns / 100k runs
constexpr char n[] = "7316717..."; // 1000 digit number
uint8_t l[1000];

// turn char array n into an array of integers
inline void build_array() { 
    for(int i = 0; i < size(n); i++) 
        l[i] = n[i] - '0';
}

const uint64_t solve() { 
	// length of adjacent digits product has to be made of
    constexpr uint8_t   DIGITS          =   13; 
    
    uint64_t            biggestProd     =   0,
                        currProd        =   1; 

    uint16_t            tail            =   0, 
                        reset           =   0; 

    
    for(uint16_t head = 0; head < 1000; head++) {
        // skip division until currProd is made up of 13 digits
        if(head >= DIGITS) { 
	        // divide out tail only if non-zero and window contains no zero
            if(l[tail] > 0 && head >= reset + DIGITS) 
                currProd /= l[tail]; 
            
            tail++; 
        }

        if(l[head] > 0) {
            currProd *= l[head];
        } 
        else {
            currProd = 1; // set it to one instead of zero, because 0 * X == 0
            reset = head; // block division until currProd contains no zero anymore
        }

        if(currProd > biggestProd) 
            biggestProd = currProd;
    }

    return biggestProd; 
}
```
