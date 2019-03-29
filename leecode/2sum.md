## Tow Sum
### Question:
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:
~~~
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
~~~

### Anwser:

``` java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result = new int[]{-1,-1};
        HashMap<Integer,Integer> tmpMap = new HashMap<Integer,Integer>(nums.lengtg);
        for ( int i = 0; i < nums.length; i++ ){
            int tmpPaired = target - nums[i];
            if( tmpMap.containsKey(tmpPaired)){
                result[1] = i;
                result[0] = tmpMap.get(tmpPaired);
            }else{
                tmpMap.put(nums[i],i);
            }
        }
        return result;
    }
}
```

### 心得
利用HashMap增加查找速度。但是会增加空间占用率