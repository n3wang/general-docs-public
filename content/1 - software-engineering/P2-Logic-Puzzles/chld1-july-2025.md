## 1534. 数好三胞胎


:d difficulty
:l https://leetcode.com/problems/count-good-triplet
:t Array  大批, Enumeration  枚举


给定一个整数 arr 和三个整数 a、 b 和 c。你需要找到好的三胞胎的数量。
如果以下条件成立，则三元组 (arr[i], arr[j], arr[k]) 是好的 ：

- 0 <= i < j < k < arr.length
- |arr[i] - arr[j]| <= a
- |arr[j] - arr[k]| <= b
- |arr[i] - arr[k]| <= c


其中 |x| 表示 x 的绝对值。
返回好的三元组的数量 。

 例 1：
```
Input: arr = [3,0,1,1,9,7], a = 7, b = 2, c = 3
Output: 4
Explanation: There are 4 good triplets: [(3,0,1), (3,0,1), (3,1,1), (0,1,1)].
```

示例 2：
```
Input: arr = [1,1,2,2,3], a = 0, b = 0, c = 1
Output: 0
Explanation: No triplet satisfies all conditions.
```



### Solution

```java
class Solution {
    public int countGoodTriplets(int[] arr, int a, int b, int c) {
        int n = arr.length, cnt = 0;
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j < n; ++j) {
                for (int k = j + 1; k < n; ++k) {
                    if (
                        Math.abs(arr[i] - arr[j]) <= a &&
                        Math.abs(arr[j] - arr[k]) <= b &&
                        Math.abs(arr[i] - arr[k]) <= c
                    ) {
                        ++cnt;
                    }
                }
            }
        }
        return cnt;
    }
}
```


```cpp
class Solution {
public:
    int countGoodTriplets(vector<int>& arr, int a, int b, int c) {
        int n = arr.size(), cnt = 0;
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j < n; ++j) {
                for (int k = j + 1; k < n; ++k) {
                    if (abs(arr[i] - arr[j]) <= a &&
                        abs(arr[j] - arr[k]) <= b &&
                        abs(arr[i] - arr[k]) <= c) {
                        ++cnt;
                    }
                }
            }
        }
        return cnt;
    }
};
```



### Pseudocode


> A flowchart of the process


## Problem Name

:d difficulty
:l link
:t tags,tags2

### Theory


### Solution


### Pseudocode


> A flowchart of the process




## Problem Name

:d difficulty
:l link
:t tags,tags2

### Theory


### Solution


### Pseudocode


> A flowchart of the process