# Oct. 1-7

## Algorithm

[https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

Given a string, find the length of the **longest substring** without repeating characters.

**Example 1:**

```text
Input: "abcabcbb"
Output: 3 
Explanation: The answer is "abc", with the length of 3. 
```

**Example 2:**

```text
Input: "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

**Example 3:**

```text
Input: "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3. 
             Note that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

1. keep a hashmap which stores the characters in string as keys and their positions as values
2. keep two pointers which define the max substring, move the right pointer to scan through the string , and update the hashmap
3. If the character is already in the hashmap, then move the left pointer to the right of the same character last found, if the index is larger than left pointer. See comments in the code

```text
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        start, end, maxlen = 0, 0, 0
        location = {}
        for end in range(len(s)):
            if s[end] in location:
                start = max(start, location[s[end]] + 1) 
                # start = location[s[end]]+1 is wrong
                # the left pointer need to move forward
                # for example, 'abba'
            maxlen = max(maxlen, end-start+1)
            location[s[end]] = end
        return maxlen
```

## Tip and Sharing

Some tricky points about slice in python

1. a\[:\] creates a new list

```text
>>> a=[1,2,3]
>>> id(a)
4564666488
>>> b=a
>>> id(b)
4564666488
>>> b=a[:]
>>> id(b)
4564703424
```

2. a\[:\] = \[...\] means in-place update of a

```text
>>> a[:] = [2,3,4]
>>> id(a)
4564666488
>>> a
[2, 3, 4]
```

