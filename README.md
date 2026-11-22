# 70. Climbing Stairs
# You are climbing a staircase. It takes n steps to reach the top.  
# Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

// class Solution {
// public:
//     int climbStairs(int n) {
//        if(n==1 || n==2){
//         return n;
//        }
//        return climbStairs(n-1) + climbStairs(n-2);
//     }
// };
// # Time Complexity: O(2ⁿ)
// # Each function call creates two more recursive calls (except base cases). This causes repeated calculations.
//
// # Space Complexity: O(n)
// # Recursive calls are stored in the call stack. The maximum recursion depth is proportional to n.

class Solution {
public:
    int climbStairs(int n) {
        if (n <= 2)
            return n;
        int a = 1;
        int b = 2;
        for (int i = 3; i <= n; i++) {
            int c = a + b;
            a = b;
            b = c;
        }
        return b;
    }
};
# Time Complexity: O(n)
# The for loop runs from 3 to n, so it executes approximately n times.

# Space Complexity: O(1)
# Only three variables (a, b, c) are used. No extra array or recursion stack is required.
