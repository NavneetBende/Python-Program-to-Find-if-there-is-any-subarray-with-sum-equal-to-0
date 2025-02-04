Subarray with sum equal to 0 in Python
Here, in this page we will discuss the program to find if there is any Subarray with sum equal to 0 in Python programming language. If such subarray is present then print True otherwise print False.

Example :

Input :  [ 4, 2, -3, 1, 6 ]
Output :  True
Explanation :  There is a subarray with zero sum from index 1 to 3, { 2+(-3)+1 = 0 }
Subarray with sum equal to 0 in Python

Method Discussed :
Method 1 : Naïve Approach
Method 2 : Using Hashing
Method 1 :
Run a outer loop for index 0 to l-1.
Run a nested loop from index i+1 to l,
Find sum, if it is equal to 0, then print True.
Otherwise, print False.
Time and Space Complexity
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in Python
Run
def subArray(arr, l):
    for i in range(l - 1):
        s = arr[i]
        for j in range(i + 1, l):
            s += arr[j]
            if s == 0:
                return True
    return False


array = [4, 2, -3, 1, 6]

print(subArray(array, len(array)))
Output
True
Method 2 :
Initialize a set s and add 0 to s
Initialize a variable total = 0
Iterate arr using for loop
For each iteration add the value to total
If total in s(set) return True
Add value of total to s
At end of for loop return False
Time and Space Complexity
Time Complexity : O(n)
Space Complexity : O(n+1)
Related Pages
Find the “Kth” max and min element of an array 

Move all the negative elements to one side of the array

Find the Union and Intersection of the two sorted arrays

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 2 : Code in Python
Run
def subArray(arr):
    s = set()
    s.add(0)

    total = 0

    for i in arr:
        total += i

        if total in s:
            return True

        s.add(total)
    return False


array = [-3, 2, 3, 1, 6]

print(subArray(array))
Output
False
