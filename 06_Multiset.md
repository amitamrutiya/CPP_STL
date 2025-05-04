## 🚀 **STL: `multiset` (Sorted Collection of Elements with Duplicates)**

#### 🧠 **What the container is used for**:

* A `multiset` is a **sorted collection** of elements where **duplicates are allowed**.
* It stores multiple copies of the same element and automatically sorts them in ascending order (by default).
* It is useful when you need to track the frequency of elements or when you have duplicates in the dataset.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store multiple occurrences of the same element.
  * You want the elements to be automatically sorted.
  * You need to perform efficient insertion, deletion, and search operations while considering duplicates.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Used in problems like counting the frequency of elements, finding common elements in two datasets, or calculating the mode of a list of numbers.
* **Real-world:** Useful in applications like word frequency analysis, maintaining logs, and multi-count data (e.g., votes, search results, etc.).

#### 🔧 **Internal data structure and behavior**:

* Internally, a `multiset` is typically implemented using a **balanced binary search tree** (e.g., a Red-Black tree).
* The elements are stored in a sorted order, and the tree structure allows logarithmic time complexity for insertions, deletions, and searches.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Automatically sorts elements.
  * Allows duplicate elements.
  * Provides efficient searching, insertion, and deletion operations.
* **Limitations**:

  * Slower than `unordered_multiset` for most operations due to the sorting.
  * Limited flexibility compared to `unordered_multiset` for frequent access operations.

#### 🚫 **When not to use it**:

* Avoid `multiset` if you don't need duplicates and need faster average-time operations (e.g., consider `unordered_set`).
* If sorting is unnecessary and faster insertion/deletion is required, `unordered_multiset` may be a better option.

---

### 🧠 **Time & Space Complexities for `multiset`**

| Operation     | Time Complexity | Space Complexity |
| ------------- | --------------- | ---------------- |
| Insertion     | O(log n)        | O(log n)         |
| Deletion      | O(log n)        | O(log n)         |
| Access/Search | O(log n)        | O(log n)         |
| Iteration     | O(n)            | O(n)             |

---

### 📚 **15 Important Methods for `multiset`**

| Method          | Description                                                         | Syntax                       | Example Usage              | Output                                     | Time Complexity |
| --------------- | ------------------------------------------------------------------- | ---------------------------- | -------------------------- | ------------------------------------------ | --------------- |
| `insert()`      | Inserts an element into the multiset.                               | `multiset.insert(val);`      | `multiset.insert(10);`     | No output (modifies multiset)              | O(log n)        |
| `erase()`       | Removes an element from the multiset.                               | `multiset.erase(val);`       | `multiset.erase(10);`      | No output (modifies multiset)              | O(log n)        |
| `find()`        | Finds an element in the multiset.                                   | `multiset.find(val);`        | `multiset.find(10);`       | Iterator or end iterator                   | O(log n)        |
| `count()`       | Returns the number of occurrences of an element.                    | `multiset.count(val);`       | `multiset.count(10);`      | `2` (if 10 appears twice)                  | O(log n)        |
| `empty()`       | Checks if the multiset is empty.                                    | `multiset.empty();`          | `multiset.empty();`        | `false`                                    | O(1)            |
| `size()`        | Returns the number of elements in the multiset.                     | `multiset.size();`           | `multiset.size();`         | `3`                                        | O(1)            |
| `clear()`       | Removes all elements from the multiset.                             | `multiset.clear();`          | `multiset.clear();`        | No output (modifies multiset)              | O(n)            |
| `begin()`       | Returns an iterator to the first element.                           | `multiset.begin();`          | `multiset.begin();`        | Iterator pointing to first element         | O(1)            |
| `end()`         | Returns an iterator to the past-the-end element.                    | `multiset.end();`            | `multiset.end();`          | Iterator past the last element             | O(1)            |
| `rbegin()`      | Returns a reverse iterator to the last element.                     | `multiset.rbegin();`         | `multiset.rbegin();`       | Reverse iterator                           | O(1)            |
| `rend()`        | Returns a reverse iterator past the first element.                  | `multiset.rend();`           | `multiset.rend();`         | Reverse iterator past the first element    | O(1)            |
| `lower_bound()` | Returns the first element that is not less than the given value.    | `multiset.lower_bound(val);` | `multiset.lower_bound(5);` | Iterator or end iterator                   | O(log n)        |
| `upper_bound()` | Returns the first element that is greater than the given value.     | `multiset.upper_bound(val);` | `multiset.upper_bound(5);` | Iterator or end iterator                   | O(log n)        |
| `equal_range()` | Returns a range of elements that are equivalent to the given value. | `multiset.equal_range(val);` | `multiset.equal_range(5);` | Pair of iterators (lower and upper bounds) | O(log n)        |
| `swap()`        | Swaps the contents of two multisets.                                | `multiset.swap(other);`      | `multiset.swap(other);`    | No output (modifies multisets)             | O(1)            |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                                            | Output     |
| ------------------------ | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------- |
| **Index-based loop**     | Not applicable (multiset is unordered, cannot access by index).                 | N/A                                                                                      | N/A        |
| **Range-based for loop** | A simple loop to iterate over the multiset elements.                            | `for (auto &val : multiset) { cout << val << " "; }`                                     | `1 5 5 10` |
| **Iterators**            | Using iterators to manually navigate through the multiset.                      | `auto it = multiset.begin(); cout << *it;`                                               | `1`        |
| **Reverse Iterators**    | Using reverse iterators to iterate backward.                                    | `for (auto it = multiset.rbegin(); it != multiset.rend(); ++it) { cout << *it << " "; }` | `10 5 5 1` |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (const auto& val : multiset) { cout << val << " "; }`                               | `1 5 5 10` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

You are given two multisets. Find their intersection and union.

1. **Intersection**: The set of elements that are present in both multisets, counting duplicates.
2. **Union**: The set of all elements from both multisets, combining duplicates.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    // Create two multisets
    multiset<int> multiset1 = {1, 5, 10, 5};
    multiset<int> multiset2 = {5, 10, 15, 5};

    // Intersection
    multiset<int> intersection;
    for (auto &val : multiset1) {
        if (multiset2.count(val) > 0) {
            intersection.insert(val);
            multiset2.erase(val); // Remove to avoid multiple insertion of the same value
        }
    }

    // Union
    multiset<int> unionSet = multiset1;
    unionSet.insert(multiset2.begin(), multiset2.end());

    // Output the intersection
    cout << "Intersection: ";
    for (auto &val : intersection) {
        cout << val << " ";
    }
    cout << endl;

    // Output the union
    cout << "Union: ";
    for (auto &val : unionSet) {
        cout << val << " ";
    }
    cout << endl;

    return 0;
}
```

#### 💡 **Output**:

```
Intersection: 5 5 10
Union: 1 5 5 5 10 10 15
```

#### ⏱️ **Time Complexity**:

* **Intersection**: O(n \* log n) for counting elements in `multiset2` for each element in `multiset1`.
* **Union**: O(n + m) for inserting elements from both multisets.
