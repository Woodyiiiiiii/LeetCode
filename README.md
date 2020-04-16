# LeetCode
My private record of Leetcode solution used by Java language.

updating...

* * * 

**Bit Manipulation**

* [136. Single Number](https://github.com/Woodyiiiiiii/LeetCode/issues/2)
* [137. Single Number II](https://github.com/Woodyiiiiiii/LeetCode/issues/3)
* [260. Single Number III](https://github.com/Woodyiiiiiii/LeetCode/issues/4)
* [191. Number of 1 Bits](https://github.com/Woodyiiiiiii/LeetCode/issues/4)
* [268. Missing Number](https://github.com/Woodyiiiiiii/LeetCode/issues/6)
* [231. Power of Two](https://github.com/Woodyiiiiiii/LeetCode/issues/7)

* * *

**Array**


* * *

**Linkedlist**


* * *

**Stack & Queue**


* * *

**Tree**


* * *

**DP**

>**According to the idea [resources](https://leetcode.com/discuss/general-discussion/458695/dynamic-programming-patterns#Minimum-(Maximum)-Path-to-Reach-a-Target).**


**1.Minimum (Maximum) Path to Reach a Target**

>Statement: Given a target find minimum (maximum) cost / path / sum to reach the target.

>Approach: Choose minimum (maximum) path among all possible paths before the current state, then add value for the current state.

>routes[i] = min(routes[i-1], routes[i-2], ... , routes[i-k]) + cost[i]


Similar Problems:

[746. Min Cost Climbing Stairs](https://github.com/Woodyiiiiiii/LeetCode/issues/8)
```
for (int i = 2; i <= n; ++i) {
   dp[i] = min(dp[i-1], dp[i-2]) + (i == n ? 0 : cost[i]);
}
 
return dp[n]
```
[64. Minimum Path Sum](https://github.com/Woodyiiiiiii/LeetCode/issues/9)
```
for (int i = 1; i < n; ++i) {
   for (int j = 1; j < m; ++j) {
       grid[i][j] = min(grid[i-1][j], grid[i][j-1]) + grid[i][j];
   }
}
 
return grid[n-1][m-1]
```
[322. Coin Change](https://github.com/Woodyiiiiiii/LeetCode/issues/10)
```
for (int j = 1; j <= amount; ++j) {
   for (int i = 0; i < coins.size(); ++i) {
       if (coins[i] <= j) {
           dp[j] = min(dp[j], dp[j - coins[i]] + 1);
       }
   }
}
```
[931. Minimum Falling Path Sum](https://github.com/Woodyiiiiiii/LeetCode/issues/11)


**2.Distinct Ways**


**3.Merging Intervals**


**4.DP on Strings**


**5.Decision Making**



* * *
