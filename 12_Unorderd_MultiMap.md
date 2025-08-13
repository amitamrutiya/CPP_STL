## 🚀 **STL: `unordered_multimap` (Hash Map for Multiple Elements)**

#### 🧠 **What the container is used for**:

* `unordered_multimap` is an **associative container** that stores multiple pairs of **keys and values**, where multiple values can be associated with the same key.
* Internally uses a **hash table** to provide fast access and insertion.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to associate **multiple values with the same key** (similar to a dictionary with duplicate entries).
  * Fast access, insertion, and deletion are necessary, and the order of elements does not matter.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Useful in problems where multiple occurrences of a key need to be tracked, like **grouping** or **counting occurrences**.
* **Real-world:** Often used in scenarios such as **word-to-synonym mapping**, **multi-tagging systems**, or **storing multiple attributes for the same entity**.

#### 🔧 **Internal data structure and behavior**:

* `unordered_multimap` is implemented using a **hash table**.
* Allows **duplicate keys**, meaning multiple entries with the same key can exist.
* The container does not maintain any specific order of elements.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Fast average-case time complexity** for insertions, deletions, and lookups (O(1)).
  * Allows **multiple entries with the same key**.
  * Efficient for operations like **grouping or counting** elements by keys.
* **Limitations**:

  * **Memory consumption** can be higher due to hash table overhead.
  * **Unordered** iteration may not be useful when maintaining the order of insertion is important.
  * Poor performance in case of **hash collisions** (O(n) in worst case).

#### 🚫 **When not to use it**:

* Avoid `unordered_multimap` when you need to maintain **sorted order** of elements by key.
* It is not suitable if **memory efficiency** is critical due to hash table overhead.

---

### 🧠 **Time & Space Complexities for `unordered_multimap`**

| Operation     | Time Complexity              | Space Complexity |
| ------------- | ---------------------------- | ---------------- |
| Insertion     | O(1) (average), O(n) (worst) | O(n)             |
| Deletion      | O(1) (average), O(n) (worst) | O(n)             |
| Access/Search | O(1) (average), O(n) (worst) | O(n)             |
| Iteration     | O(n)                         | O(n)             |

---

### 📚 **15 Important Methods for `unordered_multimap`**

| Method           | Description                                                                           | Syntax                                     | Example Usage                          | Output                                    | Time Complexity |
| ---------------- | ------------------------------------------------------------------------------------- | ------------------------------------------ | -------------------------------------- | ----------------------------------------- | --------------- |
| `insert()`       | Inserts a key-value pair into the unordered\_multimap.                                | `unordered_multimap.insert({key, value});` | `unordered_multimap.insert({5, "A"});` | No output (modifies unordered\_multimap)  | O(1)            |
| `erase()`        | Removes key-value pair(s) from the unordered\_multimap.                               | `unordered_multimap.erase(key);`           | `unordered_multimap.erase(5);`         | No output (modifies unordered\_multimap)  | O(1)            |
| `find()`         | Finds the first element by its key.                                                   | `unordered_multimap.find(key);`            | `unordered_multimap.find(5);`          | Iterator or end iterator                  | O(1)            |
| `count()`        | Returns the number of occurrences of a key.                                           | `unordered_multimap.count(key);`           | `unordered_multimap.count(5);`         | `3` (if key occurs 3 times)               | O(1)            |
| `empty()`        | Checks if the unordered\_multimap is empty.                                           | `unordered_multimap.empty();`              | `unordered_multimap.empty();`          | `false`                                   | O(1)            |
| `size()`         | Returns the number of key-value pairs in the unordered\_multimap.                     | `unordered_multimap.size();`               | `unordered_multimap.size();`           | `5`                                       | O(1)            |
| `clear()`        | Removes all key-value pairs from the unordered\_multimap.                             | `unordered_multimap.clear();`              | `unordered_multimap.clear();`          | No output (modifies unordered\_multimap)  | O(n)            |
| `begin()`        | Returns an iterator to the first element.                                             | `unordered_multimap.begin();`              | `unordered_multimap.begin();`          | Iterator to first element                 | O(1)            |
| `end()`          | Returns an iterator to the past-the-end element.                                      | `unordered_multimap.end();`                | `unordered_multimap.end();`            | Iterator past last element                | O(1)            |
| `at()`           | Accesses an element by its key.                                                       | `unordered_multimap.at(key);`              | `unordered_multimap.at(5);`            | Throws exception if not found             | O(1)            |
| `swap()`         | Swaps the contents of two unordered\_multimaps.                                       | `unordered_multimap.swap(other);`          | `unordered_multimap.swap(other);`      | No output (modifies unordered\_multimaps) | O(n)            |
| `bucket_count()` | Returns the number of buckets used by the unordered\_multimap.                        | `unordered_multimap.bucket_count();`       | `unordered_multimap.bucket_count();`   | `10` (depends on hash function)           | O(1)            |
| `load_factor()`  | Returns the average number of elements per bucket.                                    | `unordered_multimap.load_factor();`        | `unordered_multimap.load_factor();`    | `0.5` (depends on elements and buckets)   | O(1)            |
| `rehash()`       | Resizes the container to ensure that it has at least the specified number of buckets. | `unordered_multimap.rehash(n);`            | `unordered_multimap.rehash(20);`       | No output (modifies unordered\_multimap)  | O(n)            |
| `bucket()`       | Returns the bucket index of a particular element.                                     | `unordered_multimap.bucket(key);`          | `unordered_multimap.bucket(5);`        | Bucket index (int)                        | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **1D Unordered Multimap**:

  ```cpp
  unordered_multimap<int, string> umm;
  ```

* **2D Unordered Multimap (Map of Maps)**:

  ```cpp
  unordered_multimap<int, unordered_map<int, string>> umm;
  ```

* **Mixed with other STL containers**:

  ```cpp
  unordered_multimap<int, set<int>> umm;
  ```

#### 🔧 **Initialization Techniques**

* **Using curly braces**:

  ```cpp
  unordered_multimap<int, string> umm = {{1, "A"}, {2, "B"}, {3, "C"}};
  ```

* **Using `insert()`**:

  ```cpp
  unordered_multimap<int, string> umm;
  umm.insert({1, "A"});
  umm.insert({2, "B"});
  umm.insert({3, "C"});
  ```

* **Using `emplace()`**:

  ```cpp
  unordered_multimap<int, string> umm;
  umm.emplace(1, "A");
  umm.emplace(2, "B");
  umm.emplace(3, "C");
  ```

* **With custom data types or classes**:

  ```cpp
  struct Person {
      string name;
      int age;
      Person(string name, int age) : name(name), age(age) {}
  };

  unordered_multimap<int, Person> umm;
  umm.emplace(1, Person("Alice", 25));
  umm.emplace(2, Person("Bob", 30));
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                               | Example Usage                                                                                       | Output                  |
| ------------------------ | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------- |
| **Index-based loop**     | Not applicable (unordered\_multimap does not support direct indexing).    | N/A                                                                                                 | N/A                     |
| **Range-based for loop** | Iterate over elements in the unordered\_multimap.                         | `for (auto &pair : unordered_multimap) { cout << pair.first << " " << pair.second << endl; }`       | `1 A`<br>`2 B`<br>`3 C` |
| **Iterators**            | Use iterators to access elements manually.                                | `auto it = unordered_multimap.begin(); cout << it->first << " " << it->second;`                     | `1 A`                   |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability in loops. | `for (const auto& pair : unordered_multimap) { cout << pair.first << " " << pair.second << endl; }` | `1 A`<br>`2 B`<br>`3 C` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a list of **pairs of student names and subjects**, group all students by their subject and output the subject-wise student list.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <unordered_multimap>
#include <vector>
using namespace std;

void groupStudentsBySubject(const vector<pair<string, string>>& students) {
    unordered_multimap<string, string> umm;
    
    // Insert student-subject pairs
    for (auto& student : students) {
        umm.insert(student);
    }

    // Group students by subject and print
    string currentSubject;
    for (auto& pair : umm) {
        if (pair.first != currentSubject) {
            cout << "\nSubject: " << pair.first << endl;
            currentSubject = pair.first;
        }
        cout << pair.second << " ";
    }
}

int main() {
    vector<pair<string, string>> students = {{"Alice", "Math"}, {"Bob", "Science"}, {"Charlie", "Math"}, {"David", "Physics"}, {"Eva", "Math"}};
    groupStudentsBySubject(students);
    return 0;
}
```

#### 💡 **Output**:

```
Subject: Math
Alice Charlie Eva 
Subject: Science
Bob 
Subject: Physics
David 
```
