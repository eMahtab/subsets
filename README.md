# Subsets
# https://leetcode.com/problems/subsets

# Implementation :
```java
class Solution {
    public List<List<Integer>> subsets(int[] nums) {
       List<List<Integer>> list = new ArrayList<>();
       if(nums == null || nums.length == 0)
           return list;
        
       int size = 1;
       list.add(new ArrayList<Integer>());
       for(int i = size ; i <= nums.length; i++) {
           dfs(list, new ArrayList<Integer>(), nums, i, 0);
       } 
       
       return list; 
    }
    
   private void dfs(List<List<Integer>> res, List<Integer> item,
                    int[] nums, int size, int start) {
		if (item.size() == size) {
			res.add(new ArrayList<Integer>(item));
			return;
		}
	 
		for (int i = start; i < nums.length; i++) {
			item.add(nums[i]);
			dfs(res, item, nums, size, i+1);
			item.remove(item.size() - 1); // removing the last added element
		}
	}
        
}
```
