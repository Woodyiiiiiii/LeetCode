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

* [54. Spiral Matrix](https://github.com/Woodyiiiiiii/LeetCode/issues/15)
* [59. Spiral Matrix II](https://github.com/Woodyiiiiiii/LeetCode/issues/16)

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

```
for (int i = 1; i <= target; ++i) {
   for (int j = 0; j < ways.size(); ++j) {
       if (ways[j] <= i) {
           dp[i] = min(dp[i], dp[i - ways[j]] + cost / path / sum) ;
       }
   }
}
 
return dp[target]
```

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

>Statement:Given a target find a number of distinct ways to reach the target.

>Approach:Sum all possible ways to reach the current state.

>routes[i] = routes[i-1] + routes[i-2], ... , + routes[i-k]

```
for (int i = 1; i <= target; ++i) {
   for (int j = 0; j < ways.size(); ++j) {
       if (ways[j] <= i) {
           dp[i] += dp[i - ways[j]];
       }
   }
}
 
return dp[target]
```

Similar Problems:

[70. Climbing Stairs](https://github.com/Woodyiiiiiii/LeetCode/issues/12)
```
for (int stair = 2; stair <= n; ++stair) {
   for (int step = 1; step <= 2; ++step) {
       dp[stair] += dp[stair-step];   
   }
}
```
[62. Unique Paths](https://github.com/Woodyiiiiiii/LeetCode/issues/13)
```
for (int i = 1; i < m; ++i) {
   for (int j = 1; j < n; ++j) {
       dp[i][j] = dp[i][j-1] + dp[i-1][j];
   }
}
```
[1155. Number of Dice Rolls With Target Sum](https://github.com/Woodyiiiiiii/LeetCode/issues/14)
```
for (int rep = 1; rep <= d; ++rep) {
   vector<int> new_ways(target+1);
   for (int already = 0; already <= target; ++already) {
       for (int pipe = 1; pipe <= f; ++pipe) {
           if (already - pipe >= 0) {
               new_ways[already] += ways[already - pipe];
               new_ways[already] %= mod;
           }
       }
   }
   ways = new_ways;
}
```

**3.Merging Intervals**


**4.DP on Strings**


**5.Decision Making**



* * *
