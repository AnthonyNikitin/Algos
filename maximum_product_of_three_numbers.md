## Maximum Product of Three Numbers

- [maximum-product-of-three-numbers] - leetcode

```csharp
Time: O(NlogN)
Mem:  O(1)

public int MaximumProduct(int[] nums) 
{
        
    if(nums.Length == 3) {
        return nums[0] * nums[1] * nums[2];
    }

    Array.Sort(nums);
    var first = nums[0] * nums[1] * nums[nums.Length - 1];
    var second = nums[nums.Length - 3] * nums[nums.Length - 2] * nums[nums.Length - 1];

    return Math.Max(first, second);
}

```

```csharp
Time: O(N)
Mem:  O(1)

public int MaximumProduct(int[] nums) 
{
    public int MaximumProduct(int[] nums) {
        
        var min1 = int.MaxValue;
        var min2 = int.MaxValue;
        var max1 = int.MinValue;
        var max2 = int.MinValue;
        var max3 = int.MinValue;

        foreach(var n in nums) {
            if(n <= min1) {
                min2 = min1;
                min1 = n;
            }
            else if(n <= min2) {
                min2 = n;
            }

            if(n >= max1) {
                max3 = max2;
                max2 = max1;
                max1 = n;
            }
            else if(n >= max2) {
                max3 = max2;
                max2 = n;
            }
            else if(n >= max3) {
                max3 = n;
            }
        }

        return Math.Max(min1 * min2 * max1, max1 * max2 * max3);
    }
}

```



[maximum-product-of-three-numbers]: <https://leetcode.com/problems/maximum-product-of-three-numbers/>