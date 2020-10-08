Longest Palindrome

Problem description:
Given a string s which consists of lowercase or uppercase letters, return the length of the longest palindrome that can be built with those letters.

Letters are case sensitive, for example, "Aa" is not considered a palindrome here.

Example test cases:

Example 1:
Input: s = "abccccdd"
Output: 7
Explanation:
One longest palindrome that can be built is "dccaccd", whose length is 7.

Example 2:

Input: s = "a"
Output: 1
Explanation:
Since there is only 1 letter the only palindrome is "a" of length 1.

Constraints:

1 <= s.length <= 2000
s consits of lower-case and/or upper-case English letters only.

Solution using Python:

        def longestPalindrome(self, s: str) -> int:
            result, flag = 0, 0
            l=list(dict.fromkeys(s))        #creating a list of all letters in s without duplication
            for i in range(len(l)):
                count=s.count(l[i])         #getting the count of each letter from list (l) in the input string (s)
                if count%2==0:
                    result+=count           #if it is even, add count to the result 
                else:
                    flag=1                  #if any odd count shows up, keep a check
                    result+=count-1         #if count is odd, add count-1 to the result (c)
            if flag:
                result+=1                   #result needs to be incremented by 1, since one remaining character can be used in the center
                
            return result


Explanation of code:
The task is to find a symmetry with maximum possible characters in the string.
For this, we first find the counts of each character in the string and if it is even we add it to the result and if not, add count-1. 
Finally, if we encountered atleat one odd count character, we need to increment the result by 1.