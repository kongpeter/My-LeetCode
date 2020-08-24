# Plus One

## Question

Given a `non-empty` array of digits representing a non-negative integer, increment one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.


## Example

### Example 1

```
Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
```

### Example 2

```
Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
```

### Example 3

```
Input: digits = [0]
Output: [1]
```

## Constraints

> 1 <= digits.length <= 100\
> 0 <= digits[i] <= 9


## Solution

```java
class Solution {
    public int[] plusOne(int[] digits) {
        int i = digits.length - 1;
        //The last digital is not 9
        if(digits[i] != 9)
        {
            digits[i] = digits[i] + 1;
            return digits;
        }
        //All the digits are 9
        int j;
        for(j=digits.length-1;j>=0;j--)
        {
            if((j==0) && (digits[0]==9))
            {
                int[] results = new int[digits.length + 1]; //New array
                results[0]=1;
                for(int k=1;k<results.length;k++)
                {
                    results[k]=0;
                }
                return results;
            } else if (digits[j] != 9)
            {
                break;
            }
        }
        //Not all the digits are 9
        digits[j] += 1;
        j++;
        while(j < digits.length)
        {
            digits[j] = 0;
            j++;
        }
        return digits;
    }
}
```