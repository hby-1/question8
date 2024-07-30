# 存在重复元素

给你一个整数数组 `nums` 。如果任一值在数组中出现 **至少两次** ，返回 `true` ；如果数组中每个元素互不相同，返回 `false` 。

## 示例 1：
>### 输入：
>nums = [1,2,3,1]
>### 输出：
>true

## 示例 2：
>### 输入：
>nums = [1,2,3,4]
>### 输出：
>false

## 代码：

1.

    public class Solution {
        public bool ContainsDuplicate(int[] nums) {
            for(int i=0;i<nums.Length;i++){
                for(int n=i+1;n<nums.Length;n++){
                    if(nums[i]==nums[n]){
                        return true;
                    }
                }
            }
            return false;
        }
    }

2.

    public class Solution {
        public bool ContainsDuplicate(int[] nums) {
            HashSet<int> set = new HashSet<int>();
            foreach (int num in nums) {
                if (!set.Add(num)) {
                    return true;
                }
            }
            return false;
        }
    }

3.

    public class Solution {
        public bool ContainsDuplicate(int[] nums) {
            Array.Sort(nums);
            int length = nums.Length;
            for (int i = 1; i < length; i++) {
                if (nums[i] == nums[i - 1]) {
                    return true;
                }
            }
            return false;
        }
    }


