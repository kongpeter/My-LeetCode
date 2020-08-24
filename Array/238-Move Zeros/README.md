# Remove Zeros

## Question

Given an array `nums`, write a function to move all `0's` to the end of it while maintaining the relative order of the non-zero elements.


## Example 

```
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

## Notes

- You must do this **in-place** without making a copy of the array.
- Minimize the total number of operations.



## Solution: Two Recursive

```java
class Solution {
	public void moveZeroes(int[] nums) {
		if(nums==null) {
			return;
		}
		//Use j to record non-zero numbers
		int j = 0;
		for(int i=0;i<nums.length;++i) {
			if(nums[i]!=0) {
				nums[j++] = nums[i];
			}
		}
		//Change remain elements to 0
		for(int i=j;i<nums.length;++i) {
			nums[i] = 0;
		}
	}
}	
```

## Solution: One Recursive

```java
class Solution {
    public void moveZeroes(int[] nums) {

        if(nums.length <= 1)
        {
            return;
        }

        int j = 0;
        for(int i=0;i<nums.length;i++)
        {
            if(nums[i] != 0)
            {
                int temp = nums[i];
                nums[i] = nums[j];
                nums[j++] = temp;
            }
        }
    }
}
```