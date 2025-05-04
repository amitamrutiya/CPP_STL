### 🚀 **STL: `unordered_multiset` (Hash Table for Multiple Elements)**

#### 🧠 **What the container is used for**:

* `unordered_multiset` is an **associative container** that stores multiple elements of the same type.
* Unlike `unordered_set`, it allows duplicate elements (i.e., multiple identical keys).
* Internally uses a **hash table** for fast lookup and insertion.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store multiple occurrences of the same element.
  * Fast access, insertion, and deletion are needed, and the order of the elements does not matter.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Often used in problems where duplicates are allowed, such as counting the frequency of elements and problems like **finding duplicate elements**.
* **Real-world:** Useful in scenarios like **multi-item inventory management**, **tagging systems**, and **counting word occurrences**.

#### 🔧 **Internal data structure and behavior**:

* `unordered_multiset` is implemented using a **hash table**.
* Allows **multiple occurrences of the same element** in the set.
* Similar to `unordered_set`, the container does not maintain any specific order of elements.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Fast average-case time complexity** for insertions, deletions, and lookups (O(1)).
  * Useful when duplicates are allowed.
  * Ideal for counting occurrences or grouping identical items.
* **Limitations**:

  * **Memory consumption** can be higher than other containers like `set` due to hash table overhead.
  * Poor performance in case of hash collisions (O(n) in worst case).
  * **Unordered** iteration may not be useful when the order of elements is needed.

#### 🚫 **When not to use it**:

* Avoid `unordered_multiset` if you need to maintain **sorted order** of elements.
* Not suitable if **memory efficiency** is critical, due to hash table overhead.

---

### 🧠 **Time & Space Complexities for `unordered_multiset`**

| Operation     | Time Complexity              | Space Complexity |
| ------------- | ---------------------------- | ---------------- |
| Insertion     | O(1) (average), O(n) (worst) | O(n)             |
| Deletion      | O(1) (average), O(n) (worst) | O(n)             |
| Access/Search | O(1) (average), O(n) (worst) | O(n)             |
| Iteration     | O(n)                         | O(n)             |

---

### 📚 **15 Important Methods for `unordered_multiset`**

| Method           | Description                                                                           | Syntax                               | Example Usage                        | Output                                    | Time Complexity |
| ---------------- | ------------------------------------------------------------------------------------- | ------------------------------------ | ------------------------------------ | ----------------------------------------- | --------------- |
| `insert()`       | Inserts an element into the unordered\_multiset.                                      | `unordered_multiset.insert(value);`  | `unordered_multiset.insert(5);`      | No output (modifies unordered\_multiset)  | O(1)            |
| `erase()`        | Removes an element from the unordered\_multiset.                                      | `unordered_multiset.erase(value);`   | `unordered_multiset.erase(5);`       | No output (modifies unordered\_multiset)  | O(1)            |
| `find()`         | Finds an element by its value.                                                        | `unordered_multiset.find(value);`    | `unordered_multiset.find(5);`        | Iterator or end iterator                  | O(1)            |
| `count()`        | Returns the number of occurrences of a value.                                         | `unordered_multiset.count(value);`   | `unordered_multiset.count(5);`       | `3` (if value occurs 3 times)             | O(1)            |
| `empty()`        | Checks if the unordered\_multiset is empty.                                           | `unordered_multiset.empty();`        | `unordered_multiset.empty();`        | `false`                                   | O(1)            |
| `size()`         | Returns the number of elements in the unordered\_multiset.                            | `unordered_multiset.size();`         | `unordered_multiset.size();`         | `5`                                       | O(1)            |
| `clear()`        | Removes all elements from the unordered\_multiset.                                    | `unordered_multiset.clear();`        | `unordered_multiset.clear();`        | No output (modifies unordered\_multiset)  | O(n)            |
| `begin()`        | Returns an iterator to the first element.                                             | `unordered_multiset.begin();`        | `unordered_multiset.begin();`        | Iterator to first element                 | O(1)            |
| `end()`          | Returns an iterator to the past-the-end element.                                      | `unordered_multiset.end();`          | `unordered_multiset.end();`          | Iterator past last element                | O(1)            |
| `at()`           | Accesses an element by its value.                                                     | `unordered_multiset.at(value);`      | `unordered_multiset.at(5);`          | Throws exception if not found             | O(1)            |
| `swap()`         | Swaps the contents of two unordered\_multisets.                                       | `unordered_multiset.swap(other);`    | `unordered_multiset.swap(other);`    | No output (modifies unordered\_multisets) | O(n)            |
| `bucket_count()` | Returns the number of buckets used by the unordered\_multiset.                        | `unordered_multiset.bucket_count();` | `unordered_multiset.bucket_count();` | `10` (depends on hash function)           | O(1)            |
| `load_factor()`  | Returns the average number of elements per bucket.                                    | `unordered_multiset.load_factor();`  | `unordered_multiset.load_factor();`  | `0.5` (depends on elements and buckets)   | O(1)            |
| `rehash()`       | Resizes the container to ensure that it has at least the specified number of buckets. | `unordered_multiset.rehash(n);`      | `unordered_multiset.rehash(20);`     | No output (modifies unordered\_multiset)  | O(n)            |
| `bucket()`       | Returns the bucket index of a particular element.                                     | `unordered_multiset.bucket(value);`  | `unordered_multiset.bucket(5);`      | Bucket index (int)                        | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **1D Unordered Multiset**:

  ```cpp
  unordered_multiset<int> ums;
  ```

* **2D Unordered Multiset (Map of Multisets)**:

  ```cpp
  unordered_multiset<int, unordered_multiset<int>> ums;
  ```

* **Mixed with other STL containers**:

  ```cpp
  unordered_multiset<int, set<int>> ums;
  ```

#### 🔧 **Initialization Techniques**

* **Using curly braces**:

  ```cpp
  unordered_multiset<int> ums = {5, 1, 2, 5, 2, 3};
  ```

* **Using `insert()`**:

  ```cpp
  unordered_multiset<int> ums;
  ums.insert(5);
  ums.insert(1);
  ums.insert(2);
  ums.insert(5);
  ums.insert(2);
  ums.insert(3);
  ```

* **Using `emplace()`**:

  ```cpp
  unordered_multiset<int> ums;
  ums.emplace(5);
  ums.emplace(1);
  ums.emplace(2);
  ums.emplace(5);
  ums.emplace(2);
  ums.emplace(3);
  ```

* **With custom data types or classes**:

  ```cpp
  struct Person {
      string name;
      int age;
      Person(string name, int age) : name(name), age(age) {}
  };

  unordered_multiset<Person> ums;
  ums.emplace(Person("Alice", 25));
  ums.emplace(Person("Bob", 30));
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                               | Example Usage                                                             | Output                                 |
| ------------------------ | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------- |
| **Index-based loop**     | Not applicable (unordered\_multiset does not support direct indexing).    | N/A                                                                       | N/A                                    |
| **Range-based for loop** | Iterate over elements in the unordered\_multiset.                         | `for (auto &value : unordered_multiset) { cout << value << endl; }`       | `5`<br>`1`<br>`2`<br>`5`<br>`2`<br>`3` |
| **Iterators**            | Use iterators to access elements manually.                                | `auto it = unordered_multiset.begin(); cout << *it;`                      | `5`                                    |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability in loops. | `for (const auto& value : unordered_multiset) { cout << value << endl; }` | `5`<br>`1`<br>`2`<br>`5`<br>`2`<br>`3` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given an array of integers, find the **most frequent element** in the array.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <unordered_multiset>
#include <vector>
using namespace std;

int mostFrequentElement(const vector<int>& arr) {
    unordered_multiset<int> ums;
    for (int num : arr) {
        ums.insert(num);
    }

    int maxFrequency = 0;
    int result = -1;
    for (int num : arr) {
        if (ums.count(num) > maxFrequency) {
            maxFrequency = ums.count(num);
            result = num;
        }
    }
    return result;
}

int main() {
    vector<int> arr = {4, 5, 1, 2, 5, 4, 5};
    cout << "Most frequent element: " << mostFrequentElement(arr);  // Output: 5
    return 0;
}
```

#### 💡 **Output**:

```
Most frequent element: 5
```

#### ⏱️ **Time Complexity**:

* **Time Complexity:** O(n), where n is the number of elements in the array.
* **Space Complexity:** O(n), due to storing the elements in the unordered\_multiset.
