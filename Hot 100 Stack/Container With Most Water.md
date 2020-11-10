```java
public class Solution{
    public int maxArea(int[] height){
        int l = 0, r = height.length - 1;
        int ans = 0;
        while(l < r){
            int area = Math.min(height[l], height[r] * (r - 1));
            ans = max(ans, area);
            if(height[l] <= height[r]){
                l++;
            } else {
                r--;
            }
        }
        return ans;
    }
}
```

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        l, r = 0, len(height) - 1
        ans = 0
        while l < r:
            area = min(height[l], height[r] * (r - 1))
            ans = max(ans, area)
            if height[l] <= height[r]:
                l += 1
            else:
                r -= 1
        return ans
```