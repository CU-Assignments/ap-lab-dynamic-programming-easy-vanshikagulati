[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/AqLe5c87)
# Climbing Stairs
class Solution {
public:
    int climbStairs(int n) {
        if (n <= 2) return n;
        
        int prev1 = 1, prev2 = 2;
        for (int i = 3; i <= n; i++) {
            int curr = prev1 + prev2;
            prev1 = prev2;
            prev2 = curr;
        }
        return prev2;
    }
};
# Output
![Screenshot 2025-03-05 114621](https://github.com/user-attachments/assets/ea0e4672-4dc9-4628-b0d6-d3da60bd9b7a)


# Maximum Subarray
class Solution {
public:
    int maxSubArray(std::vector<int>& nums) {
        int maxSum = nums[0];
        int currentSum = nums[0];

        for (size_t i = 1; i < nums.size(); i++) {
            currentSum = std::max(nums[i], currentSum + nums[i]);
            maxSum = std::max(maxSum, currentSum);
        }

        return maxSum;
    }
};
# Output
![Screenshot 2025-03-05 114730](https://github.com/user-attachments/assets/66d5553d-d4eb-4002-9efe-dcecc072ae37)


# House Robber
#include <vector>
using namespace std;

class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        if (n == 0) return 0;
        if (n == 1) return nums[0];

        int prev2 = 0, prev1 = 0;
        
        for (int num : nums) {
            int curr = max(prev1, prev2 + num);
            prev2 = prev1;
            prev1 = curr;
        }
        
        return prev1;
    }
};
# Output
![Screenshot 2025-03-05 114809](https://github.com/user-attachments/assets/799feeec-73a0-46c8-b4fa-59b44edbb25f)


# Best Time to Buy and Sell Stock
#include <vector>
#include <climits>

using namespace std;

class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int minPrice = INT_MAX;
        int maxProfit = 0;

        for (int price : prices) {
            minPrice = min(minPrice, price); 
            maxProfit = max(maxProfit, price - minPrice);
        }

        return maxProfit;
    }
};
# Output
![Screenshot 2025-03-05 114851](https://github.com/user-attachments/assets/e1c31a33-289e-481f-bab8-bb3a28f6f78d)
