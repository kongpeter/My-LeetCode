# Fibonacci numbers

## Question

The **Fibonacci numbers**, commonly denoted ``F(n)`` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
```


## Example

**Example 1**
```
Input: 2
Output: 1
Explanation: F(2) = F(1) + F(0) = 1 + 0 = 1.
```



**Example 2**
```
Input: 3
Output: 2
Explanation: F(3) = F(2) + F(1) = 1 + 1 = 2.
```

## Solution

**Solution 1 : Recursive**

```java
class Solution {
    public int fib(int N) {
        if(N==0)
            return 0;
        else if(N==1)
            return 1;
        
        return fib(N-1)+fib(N-2);
    }
}
```

**Solution 2**

```java
class Solution {
    public int fib(int N) {
        if(N <= 0)
            return 0;
        else if(N==1 || N==2)
            return 1;

        int current = 0;
        int pre1 = 1;
        int pre2 = 1;

        for(int i=3;i<=N;i++)
        {
            current = pre1 + pre2;
            pre2 = pre1;
            pre1 = current;
        }
        return current;
    }
}
```
