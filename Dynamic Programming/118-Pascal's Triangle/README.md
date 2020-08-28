# Pascal's Triangle

Given a non-negative integer numRows, generate the first numRows of Pascal's triangle.

# Example

```
Input: 5
Output:
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
```

# Solution

```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<List<Integer>>();
        for (int i=0;i<numRows;i++){
            ArrayList<Integer> sub = new ArrayList<Integer>(); //Each row
            for (int j=0;j<=i;j++){
                //第一个位置和最后一个位置的元素为1
                if (j==0 || j==i){
                    sub.add(1);
                }else {
                    //上一行的元素进行相加
                    sub.add(result.get(i-1).get(j-1)+result.get(i-1).get(j));
                }
            }
            result.add(sub);

        }
        return result;
}
}
```