Explanation: The common factors of 10 and 15 are 1 and 5. So the answer will be 2.

Python Code:

data  = input()
li = data.split()
  
a = int(li[0])
b = int(li[1])
  
def gcd(a, b):
    if (a == 0): 
        return b; 
    return gcd(b%a, a); 
  
if (a>0 and a<(10**12+1) and b>=1 and b<(10**12+1)):
    count = 1
    for i in range(2, gcd(a, b)+1):
        if a%i==0 and b%i==0:
            count = count+1
    print(count)
Explanation:
Explanation:

We are reading two integers as a single input and then splitting it using the split() method.
The function gcd() is to find the greatest common divisor.
To know how to find the GCD of two numbers, you can go through the function gcd() which uses recursion technique. It is self-explanatory.
