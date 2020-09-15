# Intersection of Two Arrays II

Given two arrays, write a function to compute their intersection.

# Example 1

```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2,2]
```

# Example 2

```
Input: nums1 = [4,9,5], nums2 = [9,4,9,8,4]
Output: [4,9]
```

# Note:

- Each element in the result should appear as many times as it shows in both arrays.
- The result can be in any order.


# Solution

Sort two Array

```java
import java.util.*;

class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        //Assume that all arraye sorted
        Arrays.sort(nums1);
        Arrays.sort(nums2);
        if(nums1.length == 0 || nums2.length == 0)
            return new int[0];
        ArrayList<Integer> res = new ArrayList<Integer>(); //Create ArrayList
        int a = 0;
        int b = 0;
        while(a < nums1.length && b < nums2.length){
            if(nums1[a] == nums2[b]){
                res.add(nums1[a]);
                a++;
                b++;
            }else if(nums1[a] < nums2[b]){
                a++;
            }else if(nums1[a] > nums2[b])
                b++;
        }
        int[] output = new int[res.size()]; //tranfer arraylist to array
        for(int i=0;i<res.size();i++){
            output[i]=res.get(i);
        }
        return output;
    }
}
```