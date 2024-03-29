Sum of minimum absolute difference of array using python
For Finding sum of minimum absolute difference of array using Python we will take median of the given array and find out the absolute difference between median and each element of array and add all together.

Finding Minimum sum of absolute difference of given array
Here, we will discuss the following two different methods to solve this problem.

Method 1 : Naive Way
Method 2 : Efficient way
Method 1 :
import sys
Take a variable say result = sys.maxsize, to hold the required minimum sum.
Run an outer loop from index 0 to n,
Create a variable say sum = 0,
Run an inner loop from index 0 to n,
Set, sum += abs(arr[i]-arr[j])
After complete iteration of inner loop set,
result = min(result, sum).
Print result.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in Python
#Write a program to find the sum of minimum absolute difference using python
import sys

def sumOfMinAbsDifferences(arr,n):
    result = sys.maxsize
    
    for i in range(0,n):
        sum = 0;
        for j in range(0, n):
            sum += abs(arr[i]-arr[j])
        result = min(result, sum)
    return result;
         
 
# Driver code
arr = [2, 5, 4, 3]
n = len(arr)
print( "Required Sum = ", sumOfMinAbsDifferences(arr, n))
Output
Required Sum = 4
Related Pages
Determine Array is a subset of another array or not

Determine can all numbers of an array be made equal

Sort an array according to the order defined by another array 

Replace each element of the array by its rank in the array

Finding equilibrium index of an array

Method 2 :
Sort the array using inbuilt sort() function.
For the element at 0 index of array its min absolute difference is calculated using the element at index 1.
For the element at last index its min absolute difference is calculated using the 2nd last array element.
For the rest of the array elements, 1 <= i <= n-2, minimum absolute difference for an element at index i is calculated as: minAbsDiff = min( abs(arr[i] – arr[i-1]), abs(ar[i] – arr[i+1]) ).
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 2 : Code in Python
#Write a program to find the sum of minimum absolute difference using python
def sumOfMinAbsDifferences(arr,n):
    # sort the given array
    arr.sort()
    
    sum = 0
         
    sum += abs(arr[0] - arr[1]);
         
    sum += abs(arr[n - 1] - arr[n - 2]);
         
    
    for i in range(1, n - 1):
        sum += min(abs(arr[i] - arr[i - 1]),
                  abs(arr[i] - arr[i + 1]))
             
    # required sum
    return sum;
         
 
# Driver code
arr = [2, 5, 4, 3]
n = len(arr)
print( "Required Sum is", sumOfMinAbsDifferences(arr, n))
Output
Required Sum = 4
