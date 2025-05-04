## 🚀 **STL: `set` (Sorted Collection of Unique Elements)**

#### 🧠 **What the container is used for**:

* A `set` is an **ordered collection** of **unique elements**.
* It automatically sorts its elements and ensures no duplicates are present.
* It is commonly used when you need to store unique items and also want fast search, insert, and delete operations.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store unique items.
  * You need the elements to be automatically sorted.
  * You want to perform fast searches, insertions, and deletions.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Used in problems requiring uniqueness (e.g., finding duplicates, intersections, unions).
* **Real-world:** Common in scenarios where duplicate entries need to be avoided, like maintaining unique IDs, building word dictionaries, etc.

#### 🔧 **Internal data structure and behavior**:

* Internally, a `set` uses a **balanced binary search tree** (usually a Red-Black tree), which guarantees **logarithmic time complexity** for insertions, deletions, and searches.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Automatically keeps elements sorted.
  * Guarantees no duplicates.
  * Provides efficient searching, insertion, and deletion operations.
* **Limitations**:

  * Slower than an `unordered_set` for most operations, because elements are sorted.
  * Cannot store duplicate elements.
  * Limited flexibility in comparison functions (compared to other containers like `map`).

#### 🚫 **When not to use it**:

* Avoid `set` when you don't need the elements to be sorted or if you need faster average-time operations (e.g., consider `unordered_set`).
* If you need duplicate elements, `set` is not suitable.

---

### 🧠 **Time & Space Complexities for `set`**

| Operation     | Time Complexity | Space Complexity |
| ------------- | --------------- | ---------------- |
| Insertion     | O(log n)        | O(log n)         |
| Deletion      | O(log n)        | O(log n)         |
| Access/Search | O(log n)        | O(log n)         |
| Iteration     | O(n)            | O(n)             |

---

### 📚 **15 Important Methods for `set`**

| Method          | Description                                                         | Syntax                  | Example Usage         | Output                                     | Time Complexity |
| --------------- | ------------------------------------------------------------------- | ----------------------- | --------------------- | ------------------------------------------ | --------------- |
| `insert()`      | Inserts an element into the set.                                    | `set.insert(val);`      | `set.insert(10);`     | No output (modifies set)                   | O(log n)        |
| `erase()`       | Removes an element from the set.                                    | `set.erase(val);`       | `set.erase(10);`      | No output (modifies set)                   | O(log n)        |
| `find()`        | Finds an element in the set.                                        | `set.find(val);`        | `set.find(10);`       | Iterator or end iterator                   | O(log n)        |
| `count()`       | Returns the number of elements with the specified value.            | `set.count(val);`       | `set.count(10);`      | `1`                                        | O(log n)        |
| `empty()`       | Checks if the set is empty.                                         | `set.empty();`          | `set.empty();`        | `false`                                    | O(1)            |
| `size()`        | Returns the number of elements in the set.                          | `set.size();`           | `set.size();`         | `3`                                        | O(1)            |
| `clear()`       | Removes all elements from the set.                                  | `set.clear();`          | `set.clear();`        | No output (modifies set)                   | O(n)            |
| `begin()`       | Returns an iterator to the first element.                           | `set.begin();`          | `set.begin();`        | Iterator pointing to first element         | O(1)            |
| `end()`         | Returns an iterator to the past-the-end element.                    | `set.end();`            | `set.end();`          | Iterator past the last element             | O(1)            |
| `rbegin()`      | Returns a reverse iterator to the last element.                     | `set.rbegin();`         | `set.rbegin();`       | Reverse iterator                           | O(1)            |
| `rend()`        | Returns a reverse iterator past the first element.                  | `set.rend();`           | `set.rend();`         | Reverse iterator past the first element    | O(1)            |
| `lower_bound()` | Returns the first element that is not less than the given value.    | `set.lower_bound(val);` | `set.lower_bound(5);` | Iterator or end iterator                   | O(log n)        |
| `upper_bound()` | Returns the first element that is greater than the given value.     | `set.upper_bound(val);` | `set.upper_bound(5);` | Iterator or end iterator                   | O(log n)        |
| `equal_range()` | Returns a range of elements that are equivalent to the given value. | `set.equal_range(val);` | `set.equal_range(5);` | Pair of iterators (lower and upper bounds) | O(log n)        |
| `swap()`        | Swaps the contents of two sets.                                     | `set.swap(other);`      | `set.swap(other);`    | No output (modifies sets)                  | O(1)            |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                                  | Output   |
| ------------------------ | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | -------- |
| **Index-based loop**     | Not applicable (set is unordered, cannot access by index).                      | N/A                                                                            | N/A      |
| **Range-based for loop** | A simple loop to iterate over the set elements.                                 | `for (auto &val : set) { cout << val << " "; }`                                | `1 5 10` |
| **Iterators**            | Using iterators to manually navigate through the set.                           | `auto it = set.begin(); cout << *it;`                                          | `1`      |
| **Reverse Iterators**    | Using reverse iterators to iterate backward.                                    | `for (auto it = set.rbegin(); it != set.rend(); ++it) { cout << *it << " "; }` | `10 5 1` |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (const auto& val : set) { cout << val << " "; }`                          | `1 5 10` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

You are given two sets of integers. Find their intersection and union.

1. **Intersection**: The set of elements that are present in both sets.
2. **Union**: The set of all elements from both sets without duplicates.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    // Create two sets
    set<int> set1 = {1, 5, 10};
    set<int> set2 = {5, 10, 15};

    // Intersection
    set<int> intersection;
    for (auto &val : set1) {
        if (set2.find(val) != set2.end()) {
            intersection.insert(val);
        }
    }

    // Union
    set<int> unionSet = set1;
    unionSet.insert(set2.begin(), set2.end());

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
Intersection: 5 10
Union: 1 5 10 15
```

#### ⏱️ **Time Complexity**:

* **Intersection**: O(n \* log n) for finding elements in `set2` for each element in `set1`.
* **Union**: O(n + m) for inserting elements from both sets.
