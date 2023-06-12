# Arrays and strings

## Two pointers approach

### Template 1

Here's some pseudocode illustrating the concept:

```json
function fn(arr):
    left = 0
    right = arr.length - 1

    while left < right:
        Do some logic here depending on the problem
        Do some more logic here to decide on one of the following:
            1. left++
            2. right--
            3. Both left++ and right--
```

> Example 1: Given a string s, return true if it is a palindrome, false otherwise.

> A string is a palindrome if it reads the same forward as backward. That means, after reversing it, it is still the same string. For example: "abcdcba", or "racecar".

```python
def check_if_palindrome(s):
    left = 0
    right = len(s) - 1

    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1

    return True
```

This algorithm is very efficient as not only does it run in O(n), but it also uses only O(1) space. No matter how big the input is, we always only use two integer variables. The time complexity is O(n) because the while loop iterations cost O(1) each, and there can never be more than O(n) iterations of the while loop - the pointers start at a distance of n from each other and move closer by one step each iteration.

> Example 2: Given a sorted array of unique integers and a target integer, return true if there exists a pair of numbers that sum to target, false otherwise. This problem is similar to Two Sum.
For example, given nums = [1, 2, 4, 6, 8, 9, 14, 15] and target = 13, return true because 4 + 9 = 13.

```python
def check_for_target(nums, target):
    left = 0
    right = len(nums) - 1

    while left < right:
        curr = nums[left] + nums[right]
        if curr == target:
            return True
        if curr > target:
            right -= 1
        else:
            left += 1

    return False
```

Like in the previous example, this algorithm uses O(1) space and has a time complexity of O(n).

### Template 2

Here's some pseudocode illustrating the concept:

```json
function fn(arr1, arr2):
    i = j = 0
    while i < arr1.length AND j < arr2.length:
        Do some logic here depending on the problem
        Do some more logic here to decide on one of the following:
            1. i++
            2. j++
            3. Both i++ and j++

    // Step 4: make sure both iterables are exhausted
    // Note that only one of these loops would run
    while i < arr1.length:
        Do some logic here depending on the problem
        i++

    while j < arr2.length:
        Do some logic here depending on the problem
        j++
```

> Example 3: Given two sorted integer arrays arr1 and arr2, return a new array that combines both of them and is also sorted.

```python
def combine(arr1, arr2):
    ans = []
    i = j = 0
    while i < len(arr1) and j < len(arr2):
        if arr1[i] < arr2[j]:
            ans.append(arr1[i])
            i += 1
        else:
            ans.append(arr2[j])
            j += 1

    while i < len(arr1):
        ans.append(arr1[i])
        i += 1

    while j < len(arr2):
        ans.append(arr2[j])
        j += 1

    return ans
```

Like in the previous two examples, this algorithm has a time complexity of O(n) and uses O(1) space (if we don't count the output as extra space, which we usually don't).

>Example 4: [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/).

>Given two strings s and t, return true if s is a subsequence of t, or false otherwise.

>A subsequence of a string is a sequence of characters that can be obtained by deleting some (or none) of the characters from the original string, while maintaining the relative order of the remaining characters. For example, "ace" is a subsequence of "abcde" while "aec" is not.

```python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        i = j = 0
        while i < len(s) and j < len(t):
            if s[i] == t[j]:
                i += 1
            j += 1

        return i == len(s)
```

Just like all the prior examples, this solution uses O(1) space. The time complexity is linear with the lengths of s and t.