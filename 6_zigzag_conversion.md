# My solution

```python
class Solution(object):
    def convert(self, s, numRows):
        """
        :type s: str
        :type numRows: int
        :rtype: str
        """
        # Edge case !! (I forgot this.., it will be collapsed by my following alg)
        if numRows == 1:
            return s


        zigzag_arr = []
        for i in range(numRows):
            zigzag_arr.append([])

        i = 0
        dir = 1 # direction: -1 means -, +1 means +
        for s_index in range(len(s)): # for char in string
            zigzag_arr[i].append(s[s_index])
            # update the next dir
            if i == numRows-1:
                dir = -1
            elif i == 0:
                dir = 1
            # update for next position
            i += dir
        
        ans_str = ""
        for row in zigzag_arr:
            for c in row:
                ans_str += c
                
        return ans_str
```

