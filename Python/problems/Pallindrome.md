def isPalindrome(string):
     left,right=0,len(string)-1
     while right>=left:
             if not string[left]==string[right]:
                      return False
             left+=1;right-=1
             return True
>>> isPalindrome('redrum murder')
