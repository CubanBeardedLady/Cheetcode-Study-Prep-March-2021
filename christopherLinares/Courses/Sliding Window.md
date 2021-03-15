## Longest Substring Without Repeating Characters

```javascript
var lengthOfLongestSubstring = function(s) {
    let windowStart = 0;
    let max = 0;
    let dictionary = {};

    for (let windowEnd = 0; windowEnd < s.length; windowEnd++) {
        currChar = s[windowEnd];
        if (currChar in dictionary) {
            windowStart = Math.max(windowStart, dictionary[currChar] + 1)
        };
        dictionary[currChar] = windowEnd;
        max = Math.max(max, windowEnd - windowStart + 1);
    };
    return max;
};
```
