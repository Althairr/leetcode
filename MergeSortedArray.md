```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """

        # initialize the pointer to point each of the lists
        i = m - 1 # later will point to the element in nums1
        j = n - 1 # later will point to the element in nums2
        k = m + n - 1 # later will point to the nums1 to sort the array

        # while there is still an element in the nums2
        while j >= 0:
            # if the i is still greater than 0 
            # and the last number from nums1 is greater than the last number from nums2
            if i >= 0 and nums1[i] > nums2[j]:
                # place the larger numbers at the end of the nums1
                nums1[k] = nums1[i]
                # decrement the i to check the other number exists in nums1
                i -= 1
            else:
                # place the larger number in nums2 at the end of the nums1
                nums1[k] = nums2[j]
                # decrement the j to check the other number exists in nums2
                j -= 1
            # decrement the k to check the unsorted nums1
            k -= 1
```
