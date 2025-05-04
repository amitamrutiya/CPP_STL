## 🚀 **STL: `unordered_map` (Hash Table for Key-Value Pairs)**

#### 🧠 **What the container is used for**:

* An `unordered_map` is an **associative container** that stores key-value pairs.
* Unlike `map`, it does not maintain the order of the elements and is optimized for fast access based on the key.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * Fast access to elements is required (average O(1) time complexity).
  * The order of elements does not matter.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Often used in problems where you need **fast lookups**, such as counting the frequency of elements or checking if a key exists.
* **Real-world:** Used in applications like **caches**, **hash-based indexing**, and scenarios where you need **quick lookups** without regard to ordering.

#### 🔧 **Internal data structure and behavior**:

* The `unordered_map` is typically implemented using a **hash table**, where the key is hashed, and elements are stored in **buckets**.
* **No specific order** is maintained for the elements.
* Insertion and search operations are generally **constant-time**, O(1) on average, but may degrade to O(n) in case of hash collisions.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Faster average-case time complexity** for insertions, deletions, and searches (O(1)).
  * **No ordering of keys** required, which saves time.
  * **Efficient for large datasets** when order doesn't matter.
* **Limitations**:

  * May suffer **poor performance in worst-case** (O(n)) due to hash collisions.
  * **Memory usage** is typically higher compared to `map` due to the need for hashing and buckets.
  * Iteration over elements is **unordered**, so if you need sorted data, it’s not suitable.

#### 🚫 **When not to use it**:

* Avoid `unordered_map` if you need the elements to be sorted or ordered by the key.
* If **memory usage** is a concern, the hash table might consume more space than other containers like `map`.

---

### 🧠 **Time & Space Complexities for `unordered_map`**

| Operation     | Time Complexity              | Space Complexity |
| ------------- | ---------------------------- | ---------------- |
| Insertion     | O(1) (average), O(n) (worst) | O(n)             |
| Deletion      | O(1) (average), O(n) (worst) | O(n)             |
| Access/Search | O(1) (average), O(n) (worst) | O(n)             |
| Iteration     | O(n)                         | O(n)             |

---

### 📚 **15 Important Methods for `unordered_map`**

| Method           | Description                                                                           | Syntax                                | Example Usage                         | Output                                  | Time Complexity |
| ---------------- | ------------------------------------------------------------------------------------- | ------------------------------------- | ------------------------------------- | --------------------------------------- | --------------- |
| `insert()`       | Inserts a key-value pair into the unordered\_map.                                     | `unordered_map.insert({key, value});` | `unordered_map.insert({1, "apple"});` | No output (modifies unordered\_map)     | O(1)            |
| `erase()`        | Removes a key-value pair from the unordered\_map.                                     | `unordered_map.erase(key);`           | `unordered_map.erase(1);`             | No output (modifies unordered\_map)     | O(1)            |
| `find()`         | Finds an element by its key.                                                          | `unordered_map.find(key);`            | `unordered_map.find(1);`              | Iterator or end iterator                | O(1)            |
| `count()`        | Returns the number of elements with the specified key.                                | `unordered_map.count(key);`           | `unordered_map.count(1);`             | `1` (if the key exists)                 | O(1)            |
| `empty()`        | Checks if the unordered\_map is empty.                                                | `unordered_map.empty();`              | `unordered_map.empty();`              | `false`                                 | O(1)            |
| `size()`         | Returns the number of elements in the unordered\_map.                                 | `unordered_map.size();`               | `unordered_map.size();`               | `2`                                     | O(1)            |
| `clear()`        | Removes all elements from the unordered\_map.                                         | `unordered_map.clear();`              | `unordered_map.clear();`              | No output (modifies unordered\_map)     | O(n)            |
| `begin()`        | Returns an iterator to the first element.                                             | `unordered_map.begin();`              | `unordered_map.begin();`              | Iterator to first element               | O(1)            |
| `end()`          | Returns an iterator to the past-the-end element.                                      | `unordered_map.end();`                | `unordered_map.end();`                | Iterator past last element              | O(1)            |
| `at()`           | Accesses the value associated with a key.                                             | `unordered_map.at(key);`              | `unordered_map.at(1);`                | `"apple"`                               | O(1)            |
| `operator[]`     | Accesses the value associated with a key (creates a new key if it doesn't exist).     | `unordered_map[key]`                  | `unordered_map[2] = "banana";`        | `"banana"`                              | O(1)            |
| `swap()`         | Swaps the contents of two unordered\_maps.                                            | `unordered_map.swap(other);`          | `unordered_map.swap(other);`          | No output (modifies unordered\_maps)    | O(n)            |
| `bucket_count()` | Returns the number of buckets used by the unordered\_map.                             | `unordered_map.bucket_count();`       | `unordered_map.bucket_count();`       | `10` (depends on hash function)         | O(1)            |
| `load_factor()`  | Returns the average number of elements per bucket.                                    | `unordered_map.load_factor();`        | `unordered_map.load_factor();`        | `0.5` (depends on elements and buckets) | O(1)            |
| `rehash()`       | Resizes the container to ensure that it has at least the specified number of buckets. | `unordered_map.rehash(n);`            | `unordered_map.rehash(20);`           | No output (modifies unordered\_map)     | O(n)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **1D Unordered Map (Key-Value Pair)**:

  ```cpp
  unordered_map<int, string> um;
  ```

* **2D Unordered Map (Map of Maps)**:

  ```cpp
  unordered_map<int, unordered_map<int, string>> um;
  ```

* **Mixed with other STL containers**:

  ```cpp
  unordered_map<int, set<string>> um;
  ```

#### 🔧 **Initialization Techniques**

* **Using curly braces**:

  ```cpp
  unordered_map<int, string> um = {{1, "apple"}, {2, "banana"}, {3, "cherry"}};
  ```

* **Using `insert()`**:

  ```cpp
  unordered_map<int, string> um;
  um.insert({1, "apple"});
  um.insert({2, "banana"});
  um.insert({3, "cherry"});
  ```

* **Using `emplace()`** (recommended for efficiency):

  ```cpp
  unordered_map<int, string> um;
  um.emplace(1, "apple");
  um.emplace(2, "banana");
  um.emplace(3, "cherry");
  ```

* **With custom data types or classes**:

  ```cpp
  struct Person {
      string name;
      int age;
      Person(string name, int age) : name(name), age(age) {}
  };

  unordered_map<int, Person> um;
  um[1] = Person("Alice", 25);
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                               | Example Usage                                                                              | Output                                      |
| ------------------------ | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------- |
| **Index-based loop**     | Not applicable (unordered\_map does not support direct indexing).         | N/A                                                                                        | N/A                                         |
| **Range-based for loop** | Iterate over key-value pairs in the unordered\_map.                       | `for (auto &pair : unordered_map) { cout << pair.first << " : " << pair.second << endl; }` | `1 : apple`<br>`2 : banana`<br>`3 : cherry` |
| **Iterators**            | Use iterators to access key-value pairs manually.                         | `auto it = unordered_map.begin(); cout << it->first << " : " << it->second;`               | `1 : apple`                                 |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability in loops. | `for (const auto& pair : unordered_map) { cout << pair.first << " : " << pair.second; }`   | `1 : apple`<br>`2 : banana`<br>`3 : cherry` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given an array of integers, find the **first non-repeating integer** in the array.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <unordered_map>
#include <vector>
using namespace std;

int firstNonRepeating(const vector<int>& arr) {
    unordered_map<int, int> freqMap;
    for (int num : arr) {
        freqMap[num]++;
    }

    for (int num : arr) {
        if (freqMap[num] == 1) {
            return num;
        }
    }
    return -1; // Return -1 if no non-repeating number is found
}

int main() {
    vector<int> arr = {4, 5, 1, 2, 5, 4, 3};
    cout << "First non-repeating element: " << firstNonRepeating(arr);  // Output: 1
    return 0;
}
```

#### 💡 **Output**:

```
First non-repeating element: 1
```

#### ⏱️ **Time Complexity**:

* **Time Complexity:** O(n), where n is the number of elements in the array.
* **Space Complexity:** O(n), due to storing the frequencies in the unordered\_map.

---

Let me know when you're ready for the next STL container!
