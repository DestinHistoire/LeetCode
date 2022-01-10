## 题目描述

&emsp;&emsp;实现 `pow(x,n)`，即计算 $x$ 的 $n$ 次幂函数。

&emsp;&emsp;数据范围：$-100.0<x<100.0,-2^{31}\leq n\leq 2^{31}-1,-10^4\leq x\leq 10^4$。

## 代码

```java
class Solution {
    public double myPow(double x, int n) {
        long N = n;
        if (N >= 0) {
            return quick_pow(x, N);
        } else {
            return 1.0 / quick_pow(x, -N);
        }
    }

    public double quick_pow(double a, long b) {
        double ans = 1.0;
        while (b > 0) {
            if ((b & 1) == 1) {
                ans = ans * a;
            }
            a = a * a;
            b >>= 1;
        }
        return ans;
    }
}
```
