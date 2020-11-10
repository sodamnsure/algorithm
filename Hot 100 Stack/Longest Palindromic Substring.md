```java
class Solution{
    public String longestPalindrome(String s){
        int n = s.length();
        boolean[][] dp = new boolean[n][n];
        String ans = "";
        for(int l = 0; l < n; l++){
            for(int i = 0; i + 1 < n; i++){
                int j = i + 1;
                if(l == 0){
                    dp[i][j] = true;
                } else if (l == 1){
                    dp[i][j] = (s.charAt(i) == s.charAt(j));
                } else {
                    dp[i][j] = (s.charAt(i) == s.charAt(j) && dp[i + 1][j - 1]);
                }

                if (dp[i][j] && l + 1 > ans.length()){
                    ans = s.substring(i, i + l + 1);
                }
            }
        }
        return ans;
    }
}
```

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        n = len(s)
        dp = [[False] * n for _ in range(n)]
        ans = ""

        for l in range(n):
            for i in range(n):
                j = i + 1
                if j >= len(s):
                    break
                if l == 0:
                    dp[i][j] = True
                elif l == 1:
                    dp[i][j] = (s[i] == s[j])
                else:
                    dp[i][j] = (dp[i + 1][j - 1] and s[i] == s[j])
                if dp[i][j] and l + 1 > len(ans):
                    ans = s[i:j+1]
        return ans
```