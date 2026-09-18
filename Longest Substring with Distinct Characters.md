## 01. Longest Substring with Distinct Characters

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-distinct-characters-in-string5848/1)

### Problem Description

**Task:** Given a string s, find the length of the longest substring with all distinct characters.

#### Examples

##### Example 1

- **Input:**
```text
s = "geeksforgeeks"
```
- **Output:**
```text
7
```
- **Explanation:** "eksforg" is the longest substring with all distinct characters.

##### Example 2

- **Input:**
```text
s = "aaa"
```
- **Output:**
```text
1
```
- **Explanation:** "a" is the longest substring with all distinct characters.

##### Example 3

- **Input:**
```text
s = "abcdefabcbb"
```
- **Output:**
```text
6
```
- **Explanation:** The longest substring with all distinct characters is "abcdef", which has a length of 6.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-09-18 15:52:13
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    int longestUniqueSubstr(string &s) {
        // code here
        int count[26] = {0};
        int total_substring = 1;
        int first =0, second= 1;
        
        count[s[0]-'a']++;
        count[s[0]-'a'] =1;
        
        while(second <s.size()){
            
            while(count[s[second]-'a']){
                count[s[first]-'a']=0;
                first++;
                
            }
            
            count[s[second]-'a']=1;
            
            total_substring = max(total_substring, second-first+1);
            second++;
                
            
        }
        return total_substring;
    }
};
```

*Generated on: 9/18/2026, 3:52:59 PM*