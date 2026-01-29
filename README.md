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
### 4. VALID PALINDROME 
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
class Solution:
    def isPalindrome(self, s: str) -> bool:
        l=0
        r=len(s)-1
        while l<r:
            while l<r and not self.alphanum(s[l]):
                l+=1
            while r>l and not self.alphanum(s[r]):
                r-=1
            if s[l].lower()!=s[r].lower():
                return False
            l,r=l+1,r-1
        return True

        
    def alphanum(self,c):
        return (ord('A')<=ord(c)<=ord('Z')or ord('a')<=ord(c)<=ord('z') or ord('0')<=ord(c)<=ord('9') )
```
### 5. BEST TIME TO BUY AND SELL STOCK:
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        l,r=0,1
        maxP=0
        while r<len(prices):
            if prices[l]<prices[r]:
                profit=prices[r]-prices[l]
                maxP=max(maxP,profit)
            else:
                l=r
            r+=1
            
        return maxP
        
```
### 6. VALID PARENTHESES:
```
```
