## 01. Sum Two Large Numbers

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/sum-of-numbers-or-number1219/1)

### Problem Description

**Task:** Given two strings denoting non-negative numbers s1 and s2. Calculate the sum of s1 and s2.

#### Examples

##### Example 1

- **Input:**
```text
s1 = "25", s2 = "23"
```
- **Output:**
```text
"48"
```
- **Explanation:** The sum of 25 and 23 is 48.

##### Example 2

- **Input:**
```text
s1 = "2500", s2 = "23"
```
- **Output:**
```text
"2523"
```
- **Explanation:** The sum of 2500 and 23 is 2523.

##### Example 3

- **Input:**
```text
s1 = "2", s2 = "3"
```
- **Output:**
```text
"5"
```
- **Explanation:** The sum of 2 and 3 is 5.

#### Constraints

- **1.** `1 <= |s1|, |s2| <= 10⁵`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (2)

#### Solution 1 (C++)

- **Submitted:** 2026-09-19 14:45:25
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
    string findSum(string &str1, string &str2) {
        // code here
        int i = str1.size()-1; // starts from righmost digit
        int j = str2.size()-1; // starts from rightmost digit 
        int carry =0; // if any carry is found
        string ans;
        int k =0;
        
        
        while(i>=0 && j>=0){
            int digit1 = str1[i]-'0';
            int digit2 = str2[j]-'0';
            int sum = digit1 + digit2+carry;
            ans += (sum% 10) +'0';
            carry = sum/10;
            i--, j--;
            
        }
        while(i>=0){
            int digit1 = str1[i]-'0';
            int sum = digit1+carry;
            ans += (sum% 10) +'0';
            carry = sum/10;
            i--;
            
        }
        while(j>=0){
            int digit2 = str2[j]-'0';
            int sum = digit2+carry;
            
             ans += (sum% 10) +'0';
            carry = sum/10;
            j--;
            
        }
        if(carry > 0) {
                    ans += carry + '0';
                }
                
        reverse(ans.begin(), ans.end());
        // for handling the case of trailing zeros in output

        while(k<ans.size()-1 && ans[k] =='0'){
            k++;
        }
        return ans.substr(k);
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2026-09-17 23:48:31
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    string findSum(string &str1, string &str2) {
        // code here
        int i = str1.size()-1; // starts from righmost digit
        int j = str2.size()-1; // starts from rightmost digit 
        int carry =0; // if any carry is found
        string ans;
        int k =0;
        
        
        while(i>=0 && j>=0){
            int digit1 = str1[i]-'0';
            int digit2 = str2[j]-'0';
            int sum = digit1 + digit2+carry;
            ans += (sum% 10) +'0';
            carry = sum/10;
            i--, j--;
            
        }
        while(i>=0){
            int digit1 = str1[i]-'0';
            int sum = digit1+carry;
            ans += (sum% 10) +'0';
            carry = sum/10;
            i--;
            
        }
        while(j>=0){
            int digit2 = str2[j]-'0';
            int sum = digit2+carry;
            
             ans += (sum% 10) +'0';
            carry = sum/10;
            j--;
            
        }
        if(carry > 0) {
                    ans += carry + '0';
                }
                
        reverse(ans.begin(), ans.end());
        // for handling the case of trailing zeros in output

        while(k<ans.size()-1 && ans[k] =='0'){
            k++;
        }
        return ans.substr(k);
    }
};
```

*Generated on: 9/19/2026, 2:50:41 PM*