# My-Leetcodes

### 1. CONTAINS DUPLICATE
```
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        hashset=set();
        for  n in nums:
            if n in hashset:
                return True
            hashset.add(n)
        return False
```
### 2. VALID ANAGRAM
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s)!=len(t):
            return False
        countS={}
        countT={}
        for i in range (len(s)):
            countS[s[i]]=1+countS.get(s[i],0)
            countT[t[i]]=1+countT.get(t[i],0)
        for c in countS:
            if countS[c]!=countT.get(c,0):
                return False
        return True

```
### 3. TWO SUM
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap={}
        for i,n in enumerate(nums):
            diff=target-n
            if diff in hashmap:
                return [hashmap[diff],i]
            hashmap[n]=i
        
```
### 3. VALID PALINDROME 
#### a) Using Built-in Functions:
```
class Solution:
    def isPalindrome(self, s: str) -> bool:
        newStr=""
        for c in s:
            if c.isalnum():
                newStr+=c.lower()
        if newStr==newStr[::-1]:
            return True
        return False
```
#### b) Without using Built-in Functions:
```
```
