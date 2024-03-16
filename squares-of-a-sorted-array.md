## Squares of a sorted array

- [squares-of-a-sorted-array] - leetcode

```csharp
public int[] SortedSquares(int[] nums) {
        var res = new int[nums.Length];
        int left = 0;
        int right = nums.Length - 1;

        for(var i = 0; i < nums.Length; i++) {
            var currentSquare = 0;
            var l = nums[left];
            var r = nums[right];

            if(Math.Abs(l) < Math.Abs(r)) {
                currentSquare = r * r;
                right--;
            }
            else {
                currentSquare = l * l;
                left++;
            }

            res[nums.Length - 1 - i] = currentSquare;
        }


        return res;
    }

```



[squares-of-a-sorted-array]: <https://leetcode.com/problems/squares-of-a-sorted-array/>