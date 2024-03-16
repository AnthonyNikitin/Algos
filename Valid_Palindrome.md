## Valid Palindrome

- [valid-palindrome-ii] - leetcode

```csharp
Time: O(n)
Mem:  O(n)

public bool ValidPalindrome(string s) {
        
        var res = s.ToCharArray();
        
        var i = 0;
        var j = res.Length - 1;

        while(i <= j) {
            if(res[i] != res[j]) {
                return IsPalindrome(res, i, j - 1) || IsPalindrome(res, i + 1, j);
            }

            i++;
            j--;
        }

        return true;
    }

    public bool IsPalindrome(char[] res, int i, int j) {
        while(i <= j) {
            if(res[i] != res[j]) {
                return false;
            }

            i++;
            j--;
        }

        return true;
    }

```



[valid-palindrome-ii]: <https://leetcode.com/problems/valid-palindrome-ii/description/>