# Find Resultant Array After Removing Anagrams

This repository contains my Java solution for the LeetCode problem:

🔗 LeetCode Problem: https://leetcode.com/problems/find-resultant-array-after-removing-anagrams/

## 📌 Problem Statement
Given an array of strings `words`, remove all adjacent anagrams and return the remaining words.

Two strings are anagrams if they contain the same characters with the same frequency.

---

## 🚀 Approach

### Step-by-Step
1. Add the first word into the result list.
2. Compare the current word with the previous accepted word.
3. If both words are not anagrams:
   - Add the current word to the list.
   - Update the previous word.
4. Return the final list.

---

## 💡 Logic Used
- Convert strings into character arrays.
- Sort both arrays.
- Compare sorted strings.
- If equal → Anagram.
- Else → Not anagram.

---

## 🧠 Java Solution

```java
class Solution {
    public List<String> removeAnagrams(String[] words) {
        ArrayList<String> list = new ArrayList<>();
        
        String first = words[0];
        list.add(first);

        for(int i = 1; i < words.length; i++) {
            if(!isAnagram(first, words[i])) {
                list.add(words[i]);
                first = words[i];
            }
        }
        
        return list;
    }

    public static boolean isAnagram(String x, String y) {
        char ch1[] = x.toCharArray();
        char ch2[] = y.toCharArray();

        Arrays.sort(ch1);
        Arrays.sort(ch2);

        return (new String(ch1)).equals(new String(ch2));
    }
}
⏱️ Time Complexity
Sorting each word takes O(n log n)
Overall complexity depends on word length and number of words.
📚 Concepts Used
Arrays
ArrayList
Strings
Sorting
Anagram Checking
🎯 What I Learned
How to compare strings using sorting
Working with character arrays
Using helper methods for clean code
Solving string-based DSA problems in Java
🔗 GitHub Profile

https://github.com/chintalaAjay
