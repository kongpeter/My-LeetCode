# Sorted Merge LCCI

## Question

You are given two sorted arrays, A and B, where A has a large enough buffer at the end to hold B. Write a method to merge B into A in sorted order.

Initially the number of elements in A and B are m and n respectively.

## Example

```
Input:
A = [1,2,3,0,0,0], m = 3
B = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
```


## Solution

```java
class Solution {
    public void merge(int[] A, int m, int[] B, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;
        while(j >= 0)
        {      
            if(i < 0)
            {
                A[k] = B[j];
                k--;
                j--;
            }
            else if(A[i] >= B[j])
            {
                A[k] = A[i];
                k--;
                i--;
            }
            else if(A[i] < B[j])
            {
                A[k] = B[j];
                k--;
                j--;
            }
        }
    }
}
```