### Given an array Arr[] of N integers. Find the contiguous sub-array(containing at least one number) which has the maximum sum and return its sum.


*Approach 1* <br />
TC - $O(N^3)$
``` python
    #Function to find the sum of contiguous subarray with maximum sum.
    def maxSubArraySum(self,arr,N):
        ##Your code here
        maxSum = -sys.maxsize - 1
        
        for i in range(N):
            tSum = 0
            for j in range(i , N):
                tSum += arr[j]
                #print('i->', arr[i] , ' j->', arr[j], 'Sum->', tSum)
                if tSum > maxSum :
                    maxSum = tSum
        return maxSum
```
