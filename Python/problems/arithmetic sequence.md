Question:

In mathematics, when in an arithmetic sequence is a sequence of numbers such that the difference between the consecutive terms is constant then it is called arithmetic constant.

Eric was writing an arithmetic sequence with N terms, but while writing he mistakenly made one wrong entry and he is sure that the first term is right. Help him to find the wrong term entered by him.

Input:

The first line of input contains a single line T, which represents the numbers of test cases. Then the first line of each test case contains an integer N - total number of terms. And, then N space-separated integers denoting the sequence.

    Test Cases: 2

    5
    1 3 5 6 9
    
    4
    1 2 3 5

Output:

For each test case, print the wrongly entered term.

    6
    5

Constraints:

    1<=T<=100
    4<=N<=1000
    1<=Terms<=1000

Explanation:

In this question, the arithmetic sequence is given and we have to find the wrong input sequence number. So firstly we find the common difference between the sequence which is constant in arithmetic sequence and then check the sequence and find the wrong number. Mainly in this question the focus on the arithmetic sequence(AP).

To solve this question, we are using Python3.

Code:

# Input test cases
print("Enter test cases (T): ")
t = int(input())

while (t > 0):
    t -= 1

    print("Enter number of elements (N): ")
    N = int(input())

    print("Enter elements separated by spaces: ")
    arr = list(map(int, input().split()))

    # assign the values of array in different variables
    a = arr[0]
    b = arr[1]
    c = arr[2]
    d = arr[3]

    # compare the difference between the array element
    if (b - a == c - b): #find common difference
        diff = b - a
    elif(c - b == d - c):
        diff = c - b
    else :
        diff = d - a //3;

    ref = arr[0]
    
    #compare common difference with the array elements
    for i in range(1, N): 
        if (ref + diff == arr[i]):
            ref = ref + diff
        #print the wrong element in array
        else :
            print("Wrong term/number: ")
            print(arr[i])
            break

Output

      Enter test cases (T): 
      3
      Enter number of elements (N): 
      5
      Enter elements separated by spaces: 
      1 3 5 8 9
      Wrong term/number: 
      8
      Enter number of elements (N): 
      5
      Enter elements separated by spaces: 
      10 20 30 35 50
      Wrong term/number: 
      35
      Enter number of elements (N): 
      7
      Enter elements separated by spaces: 
      11 22 33 44 55 67 77
      Wrong term/number: 
      67
