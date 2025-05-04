## 🚀 **STL: `unordered_set` (Unordered Collection of Unique Elements)**

#### 🧠 **What the container is used for**:

* An `unordered_set` is a collection of **unique elements** that does **not** maintain any specific order of elements.
* It allows **fast access** and **modification** of elements based on their **hash value**, making it suitable for applications that require fast lookups, insertions, and deletions without caring about the order.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need a collection of **unique** elements and don't care about the order.
  * You need to perform **fast lookup**, **insertion**, or **deletion** operations.
  * You want average **O(1)** time complexity for these operations.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Useful in problems like checking for duplicates, implementing efficient search-based algorithms, or solving problems where element uniqueness is important (e.g., determining if two arrays have common elements).
* **Real-world:** Ideal for building hash tables, sets of unique items like tags or labels, caching mechanisms, and membership checking in a large dataset.

#### 🔧 **Internal data structure and behavior**:

* Internally, an `unordered_set` is typically implemented using a **hash table**.
* The elements are stored in **buckets** based on their hash values, which allows fast access but does not guarantee any specific order.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Fast lookups** and **insertions** due to the hash table implementation (average O(1) time complexity).
  * Ideal for operations where the order doesn't matter.
* **Limitations**:

  * **No ordering** of elements.
  * **Worst-case time complexity** for lookup, insertion, and deletion operations can be **O(n)** if hash collisions occur (though this is rare with a good hash function).
  * Larger memory consumption compared to other containers due to the hash table.

#### 🚫 **When not to use it**:

* Avoid `unordered_set` if you need **ordered** elements, in which case `set` would be a better option.
* If you have memory constraints or if the overhead of hashing might become significant for small datasets, consider using `set` or `vector`.

---

### 🧠 **Time & Space Complexities for `unordered_set`**

| Operation     | Time Complexity | Space Complexity |
| ------------- | --------------- | ---------------- |
| Insertion     | O(1) on average | O(1) on average  |
| Deletion      | O(1) on average | O(1) on average  |
| Access/Search | O(1) on average | O(1) on average  |
| Iteration     | O(n)            | O(n)             |

---

### 📚 **15 Important Methods for `unordered_set`**

| Method           | Description                                                                          | Syntax                          | Example Usage                   | Output                              | Time Complexity |
| ---------------- | ------------------------------------------------------------------------------------ | ------------------------------- | ------------------------------- | ----------------------------------- | --------------- |
| `insert()`       | Inserts an element into the unordered set.                                           | `unordered_set.insert(val);`    | `unordered_set.insert(10);`     | No output (modifies unordered\_set) | O(1)            |
| `erase()`        | Removes an element from the unordered set.                                           | `unordered_set.erase(val);`     | `unordered_set.erase(10);`      | No output (modifies unordered\_set) | O(1)            |
| `find()`         | Finds an element in the unordered set.                                               | `unordered_set.find(val);`      | `unordered_set.find(10);`       | Iterator or end iterator            | O(1)            |
| `count()`        | Returns the number of occurrences of an element (always 0 or 1 for `unordered_set`). | `unordered_set.count(val);`     | `unordered_set.count(10);`      | `1` (if 10 is present)              | O(1)            |
| `empty()`        | Checks if the unordered set is empty.                                                | `unordered_set.empty();`        | `unordered_set.empty();`        | `false`                             | O(1)            |
| `size()`         | Returns the number of elements in the unordered set.                                 | `unordered_set.size();`         | `unordered_set.size();`         | `3`                                 | O(1)            |
| `clear()`        | Removes all elements from the unordered set.                                         | `unordered_set.clear();`        | `unordered_set.clear();`        | No output (modifies unordered\_set) | O(n)            |
| `begin()`        | Returns an iterator to the first element.                                            | `unordered_set.begin();`        | `unordered_set.begin();`        | Iterator to first element           | O(1)            |
| `end()`          | Returns an iterator to the past-the-end element.                                     | `unordered_set.end();`          | `unordered_set.end();`          | Iterator past last element          | O(1)            |
| `bucket_count()` | Returns the number of buckets used by the unordered set.                             | `unordered_set.bucket_count();` | `unordered_set.bucket_count();` | Number of buckets                   | O(1)            |
| `bucket_size()`  | Returns the number of elements in a specific bucket.                                 | `unordered_set.bucket_size(n);` | `unordered_set.bucket_size(0);` | Number of elements in bucket 0      | O(1)            |
| `load_factor()`  | Returns the average number of elements per bucket.                                   | `unordered_set.load_factor();`  | `unordered_set.load_factor();`  | Load factor value                   | O(1)            |
| `rehash()`       | Resizes the container to at least `n` buckets.                                       | `unordered_set.rehash(n);`      | `unordered_set.rehash(10);`     | No output (modifies unordered\_set) | O(n)            |
| `reserve()`      | Requests a capacity of at least `n` elements.                                        | `unordered_set.reserve(n);`     | `unordered_set.reserve(10);`    | No output (modifies unordered\_set) | O(n)            |
| `swap()`         | Swaps the contents of two unordered sets.                                            | `unordered_set.swap(other);`    | `unordered_set.swap(other);`    | No output (modifies unordered\_set) | O(1)            |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                   | Output    |
| ------------------------ | ------------------------------------------------------------------------------- | --------------------------------------------------------------- | --------- |
| **Index-based loop**     | Not applicable (unordered\_set does not support indexing).                      | N/A                                                             | N/A       |
| **Range-based for loop** | A simple loop to iterate over the unordered set elements.                       | `for (auto &val : unordered_set) { cout << val << " "; }`       | `5 10 20` |
| **Iterators**            | Using iterators to manually navigate through the unordered set.                 | `auto it = unordered_set.begin(); cout << *it;`                 | `5`       |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (const auto& val : unordered_set) { cout << val << " "; }` | `5 10 20` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given an array of integers, find the first duplicate element in the array (if any).

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <unordered_set>
#include <vector>
using namespace std;

int firstDuplicate(const vector<int>& nums) {
    unordered_set<int> seen;
    for (int num : nums) {
        if (seen.count(num)) {
            return num; // Return the first duplicate
        }
        seen.insert(num);
    }
    return -1; // No duplicates found
}

int main() {
    vector<int> nums = {4, 5, 6, 4, 7, 8};
    cout << "First duplicate: " << firstDuplicate(nums) << endl; // Output: 4
    return 0;
}
```

#### 💡 **Output**:

```
First duplicate: 4
```

#### ⏱️ **Time Complexity**:

* **Time Complexity:** O(n) because both insertions and lookups in an `unordered_set` are O(1) on average.
* **Space Complexity:** O(n) due to the storage required for the `unordered_set`.

Let me know when you're ready for the next STL container, or if you'd like further clarifications!
