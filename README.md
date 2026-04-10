# Second Largest Element in Array (C++)

## 📌 Problem

Given an array of integers, find the **second largest element**.
If it does not exist, return `-1`.

---

## 🧠 Approach

* Traverse the array once.
* Keep track of:

  * `largest`
  * `secondLargest`
* Update values accordingly while avoiding duplicates.

---

## ⚙️ Algorithm

1. Initialize:

   * `largest = INT_MIN`
   * `secondLargest = INT_MIN`
2. Traverse the array:

   * If current element > largest:

     * Update secondLargest = largest
     * Update largest = current element
   * Else if current element is between largest and secondLargest:

     * Update secondLargest
3. Return `secondLargest`, or `-1` if not found.

---

## 💻 Code

```cpp
class Solution {
public:
    int secondLargestElement(vector<int>& nums) {
        if (nums.size() < 2) return -1;

        int largest = INT_MIN;
        int secondLargest = INT_MIN;

        for (int num : nums) {
            if (num > largest) {
                secondLargest = largest;
                largest = num;
            }
            else if (num < largest && num > secondLargest) {
                secondLargest = num;
            }
        }

        return (secondLargest == INT_MIN) ? -1 : secondLargest;
    }
};
```

---

## 🧪 Test Cases

| Input        | Output |
| ------------ | ------ |
| [1, 2, 3, 4] | 3      |
| [10, 10, 10] | -1     |
| [-1, -2, -3] | -2     |
| [5]          | -1     |

---

## ⏱️ Complexity

* Time: **O(n)**
* Space: **O(1)**

---

## 🚀 Author

Ranjith
