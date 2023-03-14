### Given an array Arr[] of N integers. Find the contiguous sub-array(containing at least one number) which has the maximum sum and return its sum.


*Approach 1 :-* <br/>
TC - $O(N^3)$ <br/>
Use 3 for loops 1. (i to N - 1) 2. (j to N - 1) 3. (i to j) : here calculcate the sum and compare with MaxSum

``` python
import sys
class Solution:
    #Function to find the sum of contiguous subarray with maximum sum.
    def maxSubArraySum(self,arr,N):
        maxSum =  -sys.maxsize - 1
        tSum = 0
        for i in range(N):
            for j in range(i , N):
                tSum = 0
                for k in range(i , j + 1):
                    tSum += arr[k]
                if tSum > maxSum:
                    maxSum = tSum
        return maxSum
```

*Approach 2 :-* <br/>
TC - $O(N^2)$ <br/>
Same as above but just by using 2 for loops. In the inner loop calculate sum and compare with MaxSum

``` python
    #Function to find the sum of contiguous subarray with maximum sum.
    def maxSubArraySum(self,arr,N):
        maxSum = -sys.maxsize - 1
        for i in range(N):
            tSum = 0
            for j in range(i , N):
                tSum += arr[j]
                if tSum > maxSum :
                    maxSum = tSum
        return maxSum
```

*Approach 3 :-* <br/>
TC - $O(N)$
#### Kadane's Algorithm
<br/>[Explanation :-](https://www.youtube.com/watch?v=w_KEocd__20&ab_channel=takeUforward)
<br/>
loop over array - calculate currentSum by adding current element. if currSum is negative make it 0. If positive compare with maxSum and update maxSum

``` python
import sys
class Solution:
    ##Complete this function
    #Function to find the sum of contiguous subarray with maximum sum.
    def maxSubArraySum(self,arr,N):
        currSum = 0
        maxSum = -sys.maxsize -1
        for i in range(N):
            currSum += arr[i]
            if currSum > maxSum:
                maxSum = currSum
            if currSum < 0:
                currSum = 0
        return maxSum        
```
