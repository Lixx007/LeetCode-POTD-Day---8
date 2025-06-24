# 🚀 LeetCode POTD - Day 8

<table>
<tr>
<td align="left" width="400">
  <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*VOQU8CuPG34Gsd1yJCadOQ.png" width="100%"/>
</td>
</tr>
</table>

---

## 🧙‍♂️ 2200. Find All K-Distant Indices in an Array

[Link to problem](https://leetcode.com/problems/find-all-k-distant-indices-in-an-array/)

---

## 🔥 Optimal Solution

```cpp
class Solution {
public:
    vector<int> findKDistantIndices(vector<int>& nums, int key, int k) {
        int n = nums.size();

        vector<int> result;

        for(int j = 0; j < n; j++) {
            if(nums[j] == key) {
                int start = max(j-k, 0);
                int end   = min(j+k, n-1);

                if(result.size() > 0 && result.back() >= start) {
                    start = result.back()+1;
                }

                for(int i = start; i <= end; i++) {
                    result.push_back(i);
                }
            }
        }
        return result;
    }
};



