---
tags:
  - java
  - software-engineer
---
- If you are studying this set. My suggestion is to find the code, restart it. on the vscode by finding the right file
- This set is designed to learn a language, ideally you would show the pseduocode at all times and have them practice using the pseudocode if needed.

## Power of Four
:d easy
:t Math, Bit Manipulation, Recursion
:l [Power of Four - LeetCode](https://leetcode.com/problems/power-of-four/description/)

Given an integer `n`, return _`true` if it is a power of four. Otherwise, return `false`_.
An integer `n` is a power of four, if there exists an integer `x` such that `n == 4x`

### Pseudocode
```python
Function isPowerOfFour(n):
    Convert n to binary string → binaryRepresentation
    Let count = length of binaryRepresentation - 1

    If count is not divisible by 2:
        Return false

    Else if count >= 0 AND first character of binaryRepresentation is not '1':
        Return false

    For i from 1 to count:
        If binaryRepresentation[i] is not '0':
            Return false

    Return true
```

### Solution
```java
class Solution {
    public boolean isPowerOfFour(int n) {
        String binaryRepresentation = Integer.toBinaryString(n);
        int count = binaryRepresentation.length()-1;
        if(count%2!=0){
            return false;
        }
        else if(count>=0 && binaryRepresentation.charAt(0)!='1'){
            return false;
        }

        for(int i = 1; i<count+1; i++){
            if(binaryRepresentation.charAt(i) != '0'){
                return false;
            }
        }
        return true;
    }
}
```


Given an integer `numRows`, return the first numRows of **Pascal's triangle**.
In **Pascal's triangle**, each number is the sum of the two numbers directly above it as shown:
```java
Function generate(numRows):
    Initialize triangle as an empty list of lists

    If numRows is 0:
        Return triangle

    Create firstRow with a single element [1]
    Add firstRow to triangle

    For i from 1 to numRows - 1:
        Set prevRow = triangle[i - 1]
        Initialize currentRow as a new list
        Add 1 to currentRow (first element)

        For col from 1 to i - 1:
            sum = prevRow[col - 1] + prevRow[col]
            Add sum to currentRow

        Add 1 to currentRow (last element)
        Add currentRow to triangle

    Return triangle
```
?x
```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<List<Integer>> generate(int numRows) {
        /**
         * I believe the trick is seeking if it is even or no.
         * Then we know that at first t will be 1, 2, 3, 6, 9, 15... and then continue sin reverse.
         */
         List<List<Integer>> triangle = new ArrayList<>();

        if (numRows == 0) {
            return triangle;
        }
        List<Integer> firstRow = new ArrayList<>();
        firstRow.add(1);
        triangle.add(firstRow);
        for (int i=1; i<numRows; i++){
            List<Integer> prevRow = triangle.get(i-1);
            List<Integer> currentRow = new ArrayList<Integer>();
            currentRow.add(1);
            for (int col = 1; col<i; col++){
                currentRow.add(prevRow.get(col - 1) + prevRow.get(col));
            }
            currentRow.add(1);
            triangle.add(currentRow);
        }
        return triangle;
    }
}
```



Given an integer `rowIndex`, return the `rowIndexth` (**0-indexed**) row of the **Pascal's triangle**.
In **Pascal's triangle**, each number is the sum of the two numbers directly above it as shown:
?x
```java
import java.util.ArrayList;
import java.util.List;


class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<Integer> lastRow = new ArrayList<>(List.of(1));
        if(rowIndex == 0){
            return lastRow;
        }
        for (int row = 1; row <= rowIndex; row++) {
            List<Integer> currentRow = new ArrayList<>();
            currentRow.add(1);
            for (int col = 1; col < row; col++) {
                currentRow.add(lastRow.get(col) + lastRow.get(col - 1));
            }
            currentRow.add(1);
            lastRow = currentRow;
        }
        return lastRow;
    }
}
```


Given the `root` of a binary tree, return _the preorder traversal of its nodes' values_.
?x
```java
import java.util.ArrayList;
import java.util.List;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> visit = new ArrayList<>();
        return preorderTraversalHelper(root, visit);
    }

    private List<Integer> preorderTraversalHelper(TreeNode root, List<Integer> visit) {
        if (root == null) {
            return visit;
        }
        
        visit.add(root.val);
        if (root.left != null) {
            preorderTraversalHelper(root.left, visit);
        }
        if (root.right != null) {
            preorderTraversalHelper(root.right, visit);
        }
        return visit;
    }
}
```



Given the `root` of a binary tree, return _the postorder traversal of its nodes' values_.
?x
```java
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List solution = new ArrayList<>();
        return postor(root, solution);
    }

    public List<Integer> postor(TreeNode root, List<Integer> pastTaken){
        
        if (root == null) return pastTaken;
        if(root.left != null){
            this.postor(root.left, pastTaken);
        }

        if(root.right != null){
            this.postor(root.right, pastTaken);
        }
        
        pastTaken.add(root.val);
        return pastTaken;
    }
}
```



Given the heads of two singly linked-lists headA and headB, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return null.
![[Pasted image 20250215224228.png]]
?x
```java
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        if (headA == null || headB == null) return null;
        ListNode a = headA;
        ListNode b = headB;
        // Traverse both lists. When one list ends, continue from the beginning of the other list.
        while (a != b) {
            a = (a == null) ? headB : a.next;
            b = (b == null) ? headA : b.next;
        }
        return a; // or return b, both are the same at this point
    }
}
```


Given an integer columnNumber, return its corresponding column title as it appears in an Excel sheet.
?x
```java
class Solution {
    public String convertToTitle(int columnNumber) {
        // Every 27 letters it goes it appends the specific letter.
        
        String characters = "";
        int remainder = columnNumber;
        while (remainder > 0){
            int remain = (remainder-1) % 26;
            characters= this.numberToCharacter(remain) + characters;
            // System.out.printf("%d %d", remain, characters);
            remainder = (remainder-1) / 26;
        }

        return characters;
        
    }

    public Character numberToCharacter(int number){
        /**
         * number being 1 = A
         */
        return (char) (number + (int) 'A');
    }
}
```




Given a string `columnTitle` that represents the column title as appears in an Excel sheet, return _its corresponding column number_.
?x
```java
class Solution {
    public int titleToNumber(String columnTitle) {
        int totalNumber = 0;
        for(int i=0; i<columnTitle.length(); i++){
            int index = columnTitle.length() - 1 - i;
            totalNumber += (int) Math.pow(26, i) * (columnTitle.charAt(index) - 'A' + 1);
        }
        return totalNumber;
    }
}
```


Given two integer arrays `nums1` and `nums2`, return _an array of their intersection_. Each element in the result must be **unique** and you may return the result in **any order**.
?x
```java
import java.util.ArrayList;
import java.util.HashSet;

class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        // I mean as long as the union is there then return both?
        HashSet<Integer> set = new HashSet<Integer>();
        ArrayList<Integer> intersections = new ArrayList<Integer>();
        for (int number:nums1){
            set.add(number);
        }

        for (int number:nums2){
            if(set.contains(number)){
                intersections.add(number);
                set.remove(number);
            }
        }

        int[] solution = intersections.stream().mapToInt(Integer::intValue).toArray();
        return solution;
    }
}
```


String `t` is generated by random shuffling string `s` and then add one more letter at a random position.
?x
```java
class Solution {
    public char findTheDifference(String s, String t) {
        int[] counts = new int[26];
        for (int i = 0;i<counts.length; i++){
            counts[i] = 0;
        }
        for (char letter: s.toCharArray()){
            counts[(int)letter - 'a'] += 1;
        }

        for (char letter: t.toCharArray()){
            counts[(int)letter - 'a'] -= 1;
        }

        for (int i=0;i<counts.length; i++){
            if (counts[i] != 0){
                return (char)( 'a' + i);
            }
        }

        return ' ';
    }
}
```



Given an integer array `nums` of length `n` and an integer `target`, find three integers in `nums` such that the sum is closest to `target`.
```java
import java.util.Arrays;

class Solution {
    public int threeSumClosest(int[] nums, int target) {
        // I am thinking of the following: add and compare for the closest.
        // for that you kind of need to find each calculation.  The probelm also is htat it cna be positive. Over 500 is a problem.
        // Since there are 3 numbers, we can also know thtat we can iterate by each and find. the closest.
        Arrays.sort(nums);
        int closest_value = Integer.MAX_VALUE;
        int closest_difference = Integer.MAX_VALUE;

        for (int i = 0; i<nums.length-2; i++){
            int left = i+1;
            int right = nums.length-1;
            int sub_target = target - nums[i];
            while(left < right){
                int result = nums[left] + nums[right];
                if(result > sub_target){
                    right -= 1;
                }else if(result < sub_target){
                    left += 1;
                }else{
                    // return this as this is the best possible caculation.
                    return target;
                }

                // Calculate the difference by the end of the loop
                if (Math.abs(sub_target - result) < closest_difference){
                    closest_difference = Math.abs(sub_target - result);
                    closest_value = result + nums[i];
                }
            }
        }
        return closest_value;
    }
}
```



Given a positive integer `n`, generate an `n x n` `matrix` filled with elements from `1` to `n2` in spiral order.
?x
```java
class Solution {
    public int[][] generateMatrix(int n) {
        int[][] matrix = new int[n][n];
        int digit_num = 1; // Start from 1
        int left = 0, right = n - 1, top = 0, bottom = n - 1;

        while (left<=right && top <= bottom) {
            for(int i = left; i<=right; i++){
                matrix[top][i] = digit_num++;
            }
            top++;

            for(int i = top; i<=bottom; i++){
                matrix[i][right] = digit_num++;
            }
            right--;

            if(top <= bottom){
                for(int i=right; i>=left; i--){
                    matrix[bottom][i] = digit_num++;
                }
                bottom--;
            }

            if(left <= right){
                for (int i = bottom; i>=top; i--){
                    matrix[i][left] = digit_num++;
                }
                left++;
            }

        }

        return matrix;
    }
}
```



---

##  [3342. Find Minimum Time to Reach Last Room II](https://leetcode.com/problems/find-minimum-time-to-reach-last-room-ii/)
prompt:There is a dungeon with `n x m` rooms arranged as a grid.

You are given a 2D array `moveTime` of size `n x m`, where `moveTime[i][j]` represents the **minimum** time in seconds when you can **start moving** to that room. You start from the room `(0, 0)` at time `t = 0` and can move to an **adjacent** room. Moving between **adjacent** rooms takes one second for one move and two seconds for the next, **alternating** between the two.

Return the **minimum** time to reach the room `(n - 1, m - 1)`.

Two rooms are **adjacent** if they share a common wall, either _horizontally_ or _vertically_.
```
**Input:** moveTime = [[0,4],[4,4]]

**Output:** 7

**Explanation:**

The minimum time required is 7 seconds.

- At time `t == 4`, move from room `(0, 0)` to room `(1, 0)` in one second.
- At time `t == 5`, move from room `(1, 0)` to room `(1, 1)` in two seconds.
```
![[Pasted image 20250507231231.png]]
commends:
```
```
v1pseudocode
```
class Solution {

    public int minTimeToReach(int[][] moveTime) {

        // simplest way is to see what is soonest or make a df choice

  

        /**

        DF approach:

        times = []

        functionexplore(currenttime, alternate)

            if path is end:

                times.append(curretntime)

                return

            for path in the side.. (either down or right depending on whether it exists)

                next alternate = getnext(alternate)

                choose one and explore(min(currentitime, requiredtime) + alternate, nextalternate)

  

        return min(times)

  

         */

    }

}
```
better pseudocode
```
Function minTimeToReach(grid):
    n = number of rows
    m = number of columns
    INF = large number
    minTime = 2D array of size n x m, filled with INF

    // Min-heap to always expand the earliest-reached room
    PriorityQueue pq
    pq.push([time = 0, row = 0, col = 0])

    directions = [(1, 0), (0, 1), (-1, 0), (0, -1)]  // up, down, left, right

    While pq is not empty:
        [currTime, row, col] = pq.pop()
        
        If currTime >= minTime[row][col]:
            continue

        minTime[row][col] = currTime

        If row == n-1 and col == m-1:
            return currTime  // goal reached

        For each (dr, dc) in directions:
            nextRow = row + dr
            nextCol = col + dc

            If nextRow and nextCol are within grid:
                If minTime[nextRow][nextCol] == INF:
                    stepCount = row + col + 1
                    moveCost = 1 if stepCount is odd else 2
                    waitUntil = max(currTime, grid[nextRow][nextCol])
                    arrivalTime = waitUntil + moveCost
                    pq.push([arrivalTime, nextRow, nextCol])

    return -1  // unreachable

```
?xx
```java
import java.util.*;

class Solution {
    public int minTimeToReach(int[][] moveTime) {
        int numRows = moveTime.length;
        int numCols = moveTime[0].length;
        int INF = Integer.MAX_VALUE;

        // Stores the minimum time needed to reach each cell
        int[][] minArrivalTime = new int[numRows][numCols];
        for (int[] row : minArrivalTime) {
            Arrays.fill(row, INF);
        }

        // Min-heap: stores [time, row, col], sorted by time
        PriorityQueue<int[]> minHeap = new PriorityQueue<>(Comparator.comparingInt(a -> a[0]));
        minHeap.add(new int[]{0, 0, 0}); // Start at time 0 at (0, 0)

        // Directions: up, down, left, right
        int[][] directions = {{1, 0}, {0, 1}, {-1, 0}, {0, -1}};

        while (!minHeap.isEmpty()) {
            int[] current = minHeap.poll();
            int currentTime = current[0];
            int currentRow = current[1];
            int currentCol = current[2];

            // Skip if a faster route to this cell was already found
            if (currentTime >= minArrivalTime[currentRow][currentCol]) continue;

            // Record the fastest arrival time to this cell
            minArrivalTime[currentRow][currentCol] = currentTime;

            // If we reached the goal, return the current time
            if (currentRow == numRows - 1 && currentCol == numCols - 1) return currentTime;

            for (int[] direction : directions) {
                int nextRow = currentRow + direction[0];
                int nextCol = currentCol + direction[1];

                // Check if the neighbor cell is within bounds and not yet visited
                if (nextRow >= 0 && nextRow < numRows && nextCol >= 0 && nextCol < numCols &&
                    minArrivalTime[nextRow][nextCol] == INF) {

                    int stepsTaken = currentRow + currentCol + 1; // Always increases by 1 per move
                    int moveDuration = (stepsTaken % 2 == 1) ? 1 : 2; // Alternate move cost
                    int earliestStart = Math.max(moveTime[nextRow][nextCol], currentTime);
                    int totalArrivalTime = earliestStart + moveDuration;

                    minHeap.add(new int[]{totalArrivalTime, nextRow, nextCol});
                }
            }
        }

        return -1; // Goal is unreachable
    }
}

```



### leetcodeend

---
title:
prompt:
```

```
explanation draw:
link:
shortened:
```
```
v1pseudocode
```

```
better pseudocode
```

```
?xx
```java
```




...
