```java
class Solution{
    public double findMedianSortedArrays(int[] nums1, int nums2){
        if(nums1.length > nums2.length){
            return findMedianSortedArrays(nums2, nums1);
        }

        int m = nums1.length;
        int n = nums2.length;
        int left = 0, right = m, ans1 = -1;
        int median1 = 0, median2 = 0;

        while(left <= right){
            int i = (left + right) / 2;
            int j = (m + n + 1) / 2 - i;

            int nums_im1 = (i == 0 ? Integer.MIN_VALUE : nums1[i - 1]);
            int nums_i = (i == m ? INTEGER.MAX_VALUE : nums1[i]);
            int nums_jm1 = (j == 0 ? INTEGER.MIN_VALUE : nums2[j - 1]);
            int nums_j = (j == n ? INTEGER.MAX_VALUE : nums2[j]);

            if (nums_im1 <= nums_j){
                ansi = i;
                median1 = Math.max(nums_im1, nums_jm1);
                median2 = Math.min(nums_i, nums_j);
                left = i + 1;
            } else {
                right = i - 1;
            }
        }
        return (m + n ) % 2 == 0 ？ (median1 + median2) / 2.0 : median1;
    }
}
```

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        if len(nums1) > len(nums2):
            return self.findMedianSortedArrays(nums2, nums1)
        infinty = 2**40
        m, n = len(nums1), len(nums2)
        left, right, ansi = 0, m, -1
        median1, median2 = 0, 0

        while left <= right:
            i = (left + right) // 2
            j = (m + n + 1) // 2 - i
            
            nums_im1 = (-infinty if i == 0 else nums1[i - 1])
            nums_i = (infinty if i == m else nums1[i])
            nums_jm1 = (-infinty if j == 0 else nums2[j - 1])
            nums_j = (infinty if j == n else nums2[j])

            if nums_im1 <= nums_j:
                ansi = i
                median1, median2 = max(nums_im1, nums_jm1), min(nums_i, nums_j)
                left = i + 1
            else:
                right = i - 1
        return (median1 + median2) / 2 if (m + n ) % 2 == 0 else median1
```