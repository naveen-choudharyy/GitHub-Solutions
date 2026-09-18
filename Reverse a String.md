## 01. Reverse a String

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/reverse-a-string/1)

### Problem Description

**Task:** You are given a string s, and your task is to reverse the string.

#### Examples

##### Example 1

- **Input:**
```text
s = "Geeks"
```
- **Output:**
```text
"skeeG"
```

##### Example 2

- **Input:**
```text
s = "for"
```
- **Output:**
```text
"rof"
```

##### Example 3

- **Input:**
```text
s = "a"
```
- **Output:**
```text
"a"
```

#### Constraints

- **1.** `1 <= s.size() <= 10⁶s contains only alphabetic characters (both uppercase and lowercase).`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-09-08 19:24:32
- **Status:** Correct
- **Marks:** 1

```cpp
class Solution {
  public:
    string reverseString(string& s) {
        
        int i = 0;
        int j = s.length()-1;
        
        while(i<j){
            
            int temp =s[i];
            s[i] = s[j];
            s[j] = temp;
            i++;
            j--;
        }
        return s;
    }
};
```

*Generated on: 9/18/2026, 12:13:33 PM*