##### 题目描述
Given an array with n objects colored red, white or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white and blue.

Here, we will use the integers 0, 1, and 2 to represent the color red, white, and blue respectively.

Note: You are not suppose to use the library's sort function for this problem.

Example:

Input: [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
Follow up:

A rather straight forward solution is a two-pass algorithm using counting sort.
First, iterate the array counting number of 0's, 1's, and 2's, then overwrite array with total number of 0's, then 1's and followed by 2's.
Could you come up with a one-pass algorithm using only constant space?


##### 提交链接
https://leetcode.com/problems/sort-colors/



##### 代码思路

计数+overwrite


##### 代码实现

```
class Solution {
public:
    void sortColors(vector<int>& nums) {
        if(nums.empty()==true)
            return;
        //sort(nums.begin(),nums.end());
        int cnt0=0,cnt1=0,cnt2=0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]==0)
                cnt0++;
            else if(nums[i]==1)
                cnt1++;
            else 
                cnt2++;
        }
        int i=0;
        while(cnt0--)
            nums[i++]=0;
        while(cnt1--)
            nums[i++]=1;
        while(cnt2--)
            nums[i++]=2;
        return;
        
    }
};


```
