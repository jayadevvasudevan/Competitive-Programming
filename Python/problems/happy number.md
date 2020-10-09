Happy number

Problem description:
A happy number is a number defined by the following process: 
Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Return True if n is a happy number, and False if not.

Example: 

Input: 19
Output: true
Explanation: 
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1

Solution using Python:

        def isHappy(self, n: int) -> bool:
            count=0                             
            while n != 1 and count < 10:
                n=str(n)                    # converting integer to string
                l=list(n)                   # to crate a list of all digits in n
                n=0
                for i in l:                 
                    i=int(i)
                    n=n+i*i                 # squaring and adding the digits
                count+=1
            if count==10:
                return False
            else:
                return True

Explanation of code:
Here, we set a limit on the number of loops (i.e. count < 10) to execute the code efficiently.
If before that, the happy number is found i.e. the sum of squares of digits become 1, the loop is terminated and we return True, otherwise False.
