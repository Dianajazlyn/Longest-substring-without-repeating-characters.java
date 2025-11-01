# Longest-substring-without-repeating-characters.java
class Solution {
    public int lengthOfLongestSubstring(String s) {
               Set<Character> seen = new HashSet<>();
        int left = 0, maxLen = 0;

        for (int right = 0; right < s.length(); right++) {
            char c = s.charAt(right);

            // If duplicate, move left pointer
            while (seen.contains(c)) {
                seen.remove(s.charAt(left));
                left++;
            }

            seen.add(c);
            maxLen = Math.max(maxLen, right - left + 1);
        }

        return maxLen;
    }
 }
