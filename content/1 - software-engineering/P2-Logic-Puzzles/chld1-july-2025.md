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


## 2411. 具有最大按位或运算的最小子数组

:d medium
:l https://leetcode.com/problems/smallest-subarrays-with-maximum-bitwise-o
:t Array 大批, Binary Search  二分查找, Bit Manipulation  位操作, Sliding Window  滑动窗口


You are given a 0-indexed array nums of length n, consisting of non-negative integers. For each index i from 0 to n - 1, you must determine the size of the minimum sized non-empty subarray of nums starting at i (inclusive) that has the maximum possible bitwise OR.
给定一个长度为 n 、 索引为 0 的数组 nums ，该数组由非负整数组成。对于从 0 到 n - 1 每个索引 i ，你必须确定从 i 开始（ 含 i ）的 nums 的最小非空子数组的大小，该子数组具有最大可能的按位或运算 。

In other words, let Bij be the bitwise OR of the subarray nums[i...j]. You need to find the smallest subarray starting at i, such that bitwise OR of this subarray is equal to max(Bik) where i <= k <= n - 1.
换句话说，令 B ij 为子数组 nums[i...j] 的按位或。你需要找到从 i 开始的最小子数组，使得该子数组的按位或等于 max(B ik ) 其中 i <= k <= n - 1 。
The bitwise OR of an array is the bitwise OR of all the numbers in it.
数组的按位或运算是其中所有数字的按位或运算。

Return an integer array answer of size n where answer[i] is the length of the minimum sized subarray starting at i with maximum bitwise OR.
返回大小为 n 的整数数组 answer ， 其中 answer[i] 是从 i 开始的最大按位或的最小子数组的长度 。

A subarray is a contiguous non-empty sequence of elements within an array.
子数组是数组内连续的非空元素序列。

```
Example 1:  例 1：

Input: nums = [1,0,2,1,3]
Output: [3,3,2,2,1]
Explanation:
The maximum possible bitwise OR starting at any index is 3. 
- Starting at index 0, the shortest subarray that yields it is [1,0,2].
- Starting at index 1, the shortest subarray that yields the maximum bitwise OR is [0,2,1].
- Starting at index 2, the shortest subarray that yields the maximum bitwise OR is [2,1].
- Starting at index 3, the shortest subarray that yields the maximum bitwise OR is [1,3].
- Starting at index 4, the shortest subarray that yields the maximum bitwise OR is [3].
Therefore, we return [3,3,2,2,1]. 
Example 2:  示例 2：

```

### Theory
Track all possible OR values from i to n-1 using a map of:

```java
Map<Integer, Integer> orValueToMinLength
```
where the key is the OR result and the value is the shortest length to get that OR from i.

For each step:
- Start with current number nums[i]
- For every previous OR result (from i+1), combine it with nums[i] to form new OR results
- Keep only the shortest length for each OR result
- Track which OR value reaches the maximum for this index, and record the corresponding minimum length

### Solution

```java
class Solution {
    public int[] smallestSubarrays(int[] nums) {
        int n = nums.length;
        int[] res = new int[n];

        Map<Integer, Integer> orMap = new HashMap<>(); // Map from OR value to minimal length

        for (int i = n - 1; i >= 0; i--) {
            Map<Integer, Integer> newMap = new HashMap<>();
            newMap.put(nums[i], 1);

            for (Map.Entry<Integer, Integer> entry : orMap.entrySet()) {
                int newOr = entry.getKey() | nums[i];
                int newLen = entry.getValue() + 1;
                newMap.put(newOr, Math.min(newMap.getOrDefault(newOr, Integer.MAX_VALUE), newLen));
            }

            orMap = newMap;

            int maxOr = 0;
            for (int k : orMap.keySet()) {
                maxOr = Math.max(maxOr, k);
            }
            res[i] = orMap.get(maxOr);
        }

        return res;
    }
}

```


For the bit-th binary digit:
对于第 bit 个二进制数字：

If it is 1, then after performing a bitwise OR operation with any number, this binary bit remains 1, so it has no effect.
如果是 1 ，那么与任意数字进行按位或运算后，这个二进制位依然是 1 ，所以没有任何效果。

If it is 0, then we need to find the smallest j such that j>i and the bit-th binary digit of nums[j] is 1. This way, we can achieve the maximum value through bitwise OR operations. Note that such a j may not exist.
如果是 0 ，那么我们需要找到最小的 j ，使得 j>i 和 nums[j] 的第 bit 个二进制位相等，等于 1 。这样，我们可以通过按位或运算得到最大值。注意，这样的 j 可能不存在。

Therefore, we can traverse the array nums in descending order of index, while using an array pos to record the most recent position where each binary bit was set to 1 (if no such position exists, it is initialized to −1). When we reach nums[i], for its bit-th binary digit:
因此，我们可以按索引降序遍历数组 nums ，同时使用数组 pos 记录每个二进制位最近一次被设置为 1 的位置（如果不存在这样的位置，则初始化为 −1 ）。当我们到达 nums[i] 时，对于它的第 bit 个二进制位：

If it is 1, we update pos[bit] to i.
如果是 1 ，我们将 pos[bit] 更新为 i 。

If it is 0 and pos[bit] is not −1, then to obtain the maximum bitwise OR value with i as the left boundary, the right boundary must be at least pos[bit].
如果它是 0 且 pos[bit] 不是 −1 ，那么为了获得以 i 作为左边界的最大按位或值，右边界必须至少为 pos[bit] 。

In this way, we can sequentially determine the minimum right boundary for each i as the left boundary, and thus obtain the minimum length of the subarray.
这样，我们就可以依次确定每个 i 的最小右边界作为左边界，从而得到子数组的最小长度。


```cpp
class Solution {
public:
    vector<int> smallestSubarrays(vector<int>& nums) {
        int n = nums.size();
        vector<int> pos(31, -1);
        vector<int> ans(n);
        for (int i = n - 1; i >= 0; --i) {
            int j = i;
            for (int bit = 0; bit < 31; ++bit) {
                if (!(nums[i] & (1 << bit))) {
                    if (pos[bit] != -1) {
                        j = max(j, pos[bit]);
                    }
                } else {
                    pos[bit] = i;
                }
            }
            ans[i] = j - i + 1;
        }
        return ans;
    }
};
```


### Pseudocode


> A flowchart of the process




- [ ] Remember to read english then chinese, and refer back if didnt memorize what it does. 

## Problem Name

:d difficulty
:l link
:t tags,tags2

### Theory


### Solution


### Pseudocode


> A flowchart of the process