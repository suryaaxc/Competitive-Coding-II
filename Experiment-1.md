# Experiment 1.1 : Contains Duplicate (LeetCode 217)

## AIM

To determine whether an integer array contains any duplicate element by checking if any value appears more than once in the array.

---

## ALGORITHM

1. Sort the given array in ascending order.
2. Traverse the sorted array from the first element to the second-last element.
3. Compare each element with its next adjacent element.
4. If two adjacent elements are equal, return **True** (duplicate found).
5. If no duplicates are found after completing the traversal, return **False**.

---

## CODE

```python
class Solution(object):
    def containsDuplicate(self, nums):
        nums.sort()

        for i in range(len(nums) - 1):
            if nums[i] == nums[i + 1]:
                return True

        return False
```

---

## TIME COMPLEXITY

* Sorting: O(n log n)
* Traversal: O(n)
* Overall: O(n log n)

----
----

# Experiment 1.2 : Contains Duplicate II (LeetCode 219)

## AIM

To determine whether an integer array contains duplicate elements such that the difference between their indices is less than or equal to a given value **k**.

---

## ALGORITHM

1. Create an empty dictionary to store the latest index of each element.
2. Traverse the array from the first element to the last.
3. For each element:

   * Check if it already exists in the dictionary.
   * If it exists, calculate the difference between the current index and its previous index.
   * If the difference is less than or equal to **k**, return **True**.
4. Update the element's index in the dictionary.
5. If no such duplicate pair is found after traversing the entire array, return **False**.

---

## CODE

```python
class Solution(object):
    def containsNearbyDuplicate(self, nums, k):
        d = {}
        for i in range(len(nums)):
            if nums[i] in d:
                if i - d[nums[i]] <= k:
                    return True
            d[nums[i]] = i
        return False
```

---

## TIME COMPLEXITY

* O(n), where n is the number of elements in the array.
---
