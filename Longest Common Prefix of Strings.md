## 01. Longest Common Prefix of Strings

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-common-prefix-in-an-array5129/1)

### Problem Description

**Task:** Given an array of strings arr[]. Return the longest common prefix among each and every strings present in the array. If there's no prefix common in all the strings, return "".Examples :Input: arr[] = ["geeksforgeeks", "geeks", "geek", "geezer"]

#### Examples

##### Example 1

- **Output:**
```text
""
```
- **Explanation:** There's no common prefix in the given strings.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n*min(|arri|))
- **Expected Auxiliary Space Complexity:** O(min(|arri|))

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-09-19 14:34:38
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    string longestCommonPrefix(vector<string> arr) {
        // your code here
        // vertical scanning approach
        if (arr.empty())
        return "";
        
        
        int count =0;
        for(int i=0; i<arr[0].size(); i++){ // it takes single words from geeksforgeeks
            char ch = arr[0][i];
           for(int j=1; j<arr.size(); j++){
               
            if(i >=arr[j].size() || arr[j][i] != ch)  {
                return arr[0].substr(0,count);
            } 
           } 
           count++;
        }
    
        return arr[0].substr(0, count);
    }
    
};
```

*Generated on: 9/19/2026, 2:35:06 PM*