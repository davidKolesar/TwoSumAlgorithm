# Two Sum Explanation
======

### Problem Description :

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.



# Solution
======


class Solution {

    public int[] twoSum(int[] nums, int target) {
    
    Map<Integer,Integer> map = new HashMap<>();
    
        for(int i =0; i< nums.length; i++) {
			//Checking if the map already contains the complement
			if(map.containsKey(target - nums[i])){
                return new int[]{map.get(target - nums[i]), i};
            } else {
		//if not, store the ith element and its index in the map
                map.put(nums[i], i);
            }
        }
        return null;
    }

### Why use a hashmap instead of just sorting with Arrays.sort() ? 


Hashmaps have constant time lookup, which results in linear run time.

If you used an array, it wouldn't be linear beause it has to search).

### Why?

HashMap relies on a very efficient algorithm called "hashing." Essentially the way it works is to split the items in the collection into much smaller groups which can be accessed extremely quickly. Once the group is located a less efficient search mechanism can be used to locate the specific item.

Identifying the group for an item occurs via an algorithm called a 'hashing function'. Hashing is the process of converting data — text, numbers, files, or anything, really — into a fixed-length string of letters and numbers. Data is converted into these fixed-length strings, or hash values, by using a special algorithm called a hash function.

In Java the hashing method is Object.hashCode() which returns an int representing the group (which is very efficient).
