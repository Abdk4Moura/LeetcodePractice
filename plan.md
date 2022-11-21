# Leetcode questions

## 1
- Q1. Find minimum X such that ((A|X)&(B|X)) == C given A, B, and C, if exits otherwise return -1.

Q2. Given a binary array of 0s/1s count all subarrays having atleast one 0. 
    Also maximum one operation is allowed to convert 1 => 0 for any element in the given array 
    such that the number of subarrays with at least one 0 is maximized. 

Question 2:
First of all, calculate all the subarrays that have at least one 0 in them. This can be done by removing all the subarrays which contain only 1's from the total subarrays.
Then, iterate for every position of 1 and try to change it to 0, and calculate the answer. Let's say we want to flip the 1 at the ith index, so we just want to add the number of increased subarrays.
For example, in 101111100 if we flip 1 at the 5th index we will add subarrays only from index 3 to index 7 including the 5th index as it has 0.
Mathematically, the number of subarrays added is (number of continuous 1's from left till i) * (number of continuous 1's from right after i).

## 2
Given 2x4 matrix it contains numbers in the range 1-8.
For example:

[[4,2,6,5],
 [1,8,7,3]]

You have 3 operations:

    Rotate: Middle 4 numbers rotate in clockwise manner.
    [4,2,6,5  
    1,8,7,3]  
    becomes  
    [4,8,2,5  
    1,7,6,3]  

    Swap: swaps the two arrays  
    [4,2,6,5  
    1,8,7,3]  
    becomes  
    [1,8,7,3  
    4,2,6,5]  

    Shift (right):  
    [4,2,6,5  
    1,8,7,3]  
    becomes  
    [5,4,2,6,  
    3,1,8,7]  

Your goal is to reach following state and return how many minimum operations would it take to reach that state.

[[1,2,3,4],  
 [5,6,7,8]]  

Similar questions:

- [sliding puzzle][a]
- [open the lock][b]

## 3
### Third question:
[Google Singapore Internship OA Round][c]

## 4
### Max Consecutive Ones
This [problem][max-consecutive] is referred to as the most similar problem to a Google Internship Problem on 22 August [here][max-here]

## 5
### [Shortest Way to Form a String][shortest-wtfs]

**Question **

Given two string, say ``A` = "abca"`, ``B` = "abbac"`. We can make another string ``S`` by concatening ``A`` multiple times. Then we can remove any number of charaters from string `S`.
Is it possible to make string `S` equal to `B`? Return true or false.

I completed it by only check if all unique characters from `B` exists in `A` or not and then return True or False.

Follow Up: What is the minimum number of times you need to concate if the given inputs are always True from the first question?
I approachedO(n*m) solution. The interviewer was happy with this and told to write code for this approach.
I messed up when coding but at the end I could implement my idea. I checked and tested my code. Everything was fine.

Then I proposed another solution when I had only 2/3 mins which take O(max(n, m)) time complexity. And it was the best solution. He was happy taking my interview.

Real question [here][shortest-wtfs-q]

## 6
### Minimum Steps to reach the end of Array
[Minimum Steps to reach the end of Array][min]  
A = [1, 0 , 0, 7, 1, 2, 2, 2, 3 ,7]  
Start at index 0.  
You may travel to indx i - 1, index i + 1 or any index j where A[i] == A[j]  
The goal is return the min step to reach the last elemt  
The expected output is 3  
[0, 4, 3, 9]->3  

Related problems:

[https://leetcode.com/problems/jump-game-ii/][jump-game-ii]

## 7
### Minimum Steps to reach destination
[Minimum Steps to reach destination][min-1]
Given a grid with obstacles, a robot with its starting point(si, sj) and a destination(di, dj), find the minimum steps to the destination from starting point. Provided robot can go in all four directions from starting point but once a direction is chosen it can only change its direction when it hits a boundary. For eg, if it chose left, it will go on in left direction till it hits the boundary, now it will again choose a direction(up or down) and continue till it hits the boundary and so on till it reaches the destination.
Here, boundary is either an obstacle or end of the grid
one step is equal to number of change in directions.

```
0 0 1 0 0
0 0 0 S 0
0 D 0 1 0
1 1 0 1 1
0 0 0 0 0
```

In this grid, answer will be 2. First move left, hit the the boundary, move down(step 1), hit the obstacle, move left(step 2), reach destination.

Most-similar Leetcode question:[https://leetcode.com/problems/the-maze-ii/][maze-ii]

[a]:https://leetcode.com/problems/sliding-puzzl e
[b]:https://leetcode.com/problems/open-the-lock
[c]:https://leetcode.com/discuss/interview-question/2675295/Google-Singapore-Internship-OA-Round-for-2023-or-8th-oct-or-Solutions-attached
[max-consecutive]:https://leetcode.com/problems/max-consecutive-ones-iii/submissions/
[shortest-wtfs]:[https://leetcode.com/discuss/interview-question/1200891/Google-or-Minimum-steps-to-make-a-target-string]
[shortest-wtfs-q]:[https://leetcode.com/problems/shortest-way-to-form-string/]
[min]:https://leetcode.com/discuss/interview-question/450018/Google-or-Phone-or-Min-step-to-reach-the-end-of-array
[jump-game-ii]:https://leetcode.com/problems/jump-game-ii/
[min-1]:https://leetcode.com/discuss/interview-question/647724/Google-or-Phone-or-Minimum-steps-to-destination
[maze-ii]:https://leetcode.com/problems/the-maze-ii/
