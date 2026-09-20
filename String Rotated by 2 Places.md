## 01. String Rotated by 2 Places

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/check-if-string-is-rotated-by-two-places-1587115620/1)

### Problem Description

**Task:** Given two strings s1 and s2. Return true if the string s2 can be obtained by rotating (in any direction) string s1 by exactly 2 places, otherwise, false.Note: Both rotations should be performed in same direction chosen initially.Examples:Input: s1 = "amazon", s2 = "azonam"

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** "amazon" can be rotated anti-clockwise by two places, which will make it as "azonam".

##### Example 2

- **Input:**
```text
s1 = "geeksforgeeks", s2 = "geeksgeeksfor"
```
- **Output:**
```text
trueExplanation: If we rotate "ab" by two place in any direction, we always get "ab".
```
- **Explanation:** If we rotate "geeksforgeeks" by two place in any direction, we won't get "geeksgeeksfor".Input: s1 = "ab", s2 = "ab"

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-09-20 11:45:30
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    bool isRotated(string& s1, string& s2) {

        if (s1.size() != s2.size())
            return false;

        int n = s1.size();

        // Anti-clockwise rotation by 2 places
        bool anticlockwise = true;

        for (int i = 0; i < n; i++) {
            if (s1[i] != s2[(i + 2) % n]) {
                anticlockwise = false;
                break;
            }
        }

        if (anticlockwise)
            return true;


        // Clockwise rotation by 2 places
        bool clockwise = true;

        for (int i = 0; i < n; i++) {
            if (s1[i] != s2[(i - 2 + n) % n]) {
                clockwise = false;
                break;
            }
        }

        return clockwise;
    }
};
```

*Generated on: 9/20/2026, 11:46:14 AM*