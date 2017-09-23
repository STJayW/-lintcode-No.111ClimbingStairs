# -lintcode-No.111ClimbingStairs
use dynamicprogramming solve the problem

Description :
    You are climbing a stair case. It takes n steps to reach to the top.
    Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
    
Example :
    Given an example n=3 , 1+1+1=2+1=1+2=3
    return 3
    
Answer :

    class Solution:
    """
    @param n: An integer
    @return: An integer
    """
    def climbStairs(self, n):
        # write your code here
        if n <3:
            return n
        dp = [0]*(n+1)
        dp[1] = 1
        dp[2] = 2
        for i in range(3,n+1):
            dp[i] = (dp[i-2] + dp[i-1])
        return dp[n]
