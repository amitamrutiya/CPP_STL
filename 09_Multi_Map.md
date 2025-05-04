## 🚀 **STL: `multimap` (Associative Container for Multiple Key-Value Pairs)**

#### 🧠 **What the container is used for**:

* A `multimap` is an **associative container** that stores key-value pairs, similar to a `map`, but allows multiple elements with the same key.
* It is useful when you need to store and retrieve values associated with **non-unique keys**.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store multiple values for the same key.
  * The order of elements in the container is still important and should be maintained automatically.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Used when dealing with problems where one key can map to multiple values, such as counting occurrences of words or mapping multiple entries to a single identifier.
* **Real-world:** Useful in applications like **event logging**, where one event may have multiple timestamps or associated actions, or in databases where multiple records can have the same key.

#### 🔧 **Internal data structure and behavior**:

* A `multimap` is typically implemented as a **self-balancing binary search tree** (e.g., **Red-Black Tree**), like `map`, but allows duplicates for keys.
* The elements in a `multimap` are always sorted by the **key**, and values with the same key are stored in the order of their insertion.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Allows duplicate keys**: Multiple key-value pairs with the same key are allowed.
  * **Sorted keys**: The elements are automatically sorted based on the key.
  * Provides **O(log n)** time complexity for search, insertion, and deletion.
* **Limitations**:

  * **Slower than unordered containers** like `unordered_multimap` in terms of insertion and lookup time (O(log n) vs. O(1)).
  * Requires more memory due to the tree structure.

#### 🚫 **When not to use it**:

* Avoid `multimap` if you don’t need to allow **duplicate keys** and need **fast access** (use `map` or `unordered_map` instead).
* If **memory** usage is a concern, consider using `unordered_multimap`, which may be more efficient.

---

### 🧠 **Time & Space Complexities for `multimap`**

| Operation     | Time Complexity | Space Complexity |
| ------------- | --------------- | ---------------- |
| Insertion     | O(log n)        | O(log n)         |
| Deletion      | O(log n)        | O(log n)         |
| Access/Search | O(log n)        | O(log n)         |
| Iteration     | O(n)            | O(n)             |

---

### 📚 **15 Important Methods for `multimap`**

| Method          | Description                                                                       | Syntax                           | Example Usage                    | Output                           | Time Complexity |
| --------------- | --------------------------------------------------------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- | --------------- |
| `insert()`      | Inserts a key-value pair into the multimap.                                       | `multimap.insert({key, value});` | `multimap.insert({1, "apple"});` | No output (modifies multimap)    | O(log n)        |
| `erase()`       | Removes a key-value pair from the multimap.                                       | `multimap.erase(key);`           | `multimap.erase(1);`             | No output (modifies multimap)    | O(log n)        |
| `find()`        | Finds an element by its key.                                                      | `multimap.find(key);`            | `multimap.find(1);`              | Iterator or end iterator         | O(log n)        |
| `count()`       | Returns the number of elements with the specified key.                            | `multimap.count(key);`           | `multimap.count(1);`             | `2` (if duplicates exist)        | O(log n)        |
| `empty()`       | Checks if the multimap is empty.                                                  | `multimap.empty();`              | `multimap.empty();`              | `false`                          | O(1)            |
| `size()`        | Returns the number of elements in the multimap.                                   | `multimap.size();`               | `multimap.size();`               | `2`                              | O(1)            |
| `clear()`       | Removes all elements from the multimap.                                           | `multimap.clear();`              | `multimap.clear();`              | No output (modifies multimap)    | O(n)            |
| `begin()`       | Returns an iterator to the first element.                                         | `multimap.begin();`              | `multimap.begin();`              | Iterator to first element        | O(1)            |
| `end()`         | Returns an iterator to the past-the-end element.                                  | `multimap.end();`                | `multimap.end();`                | Iterator past last element       | O(1)            |
| `at()`          | Accesses the value associated with a key.                                         | `multimap.at(key);`              | `multimap.at(1);`                | `"apple"`                        | O(log n)        |
| `operator[]`    | Accesses the value associated with a key (creates a new key if it doesn't exist). | `multimap[key]`                  | `multimap[2] = "banana";`        | `"banana"`                       | O(log n)        |
| `swap()`        | Swaps the contents of two multimaps.                                              | `multimap.swap(other);`          | `multimap.swap(other);`          | No output (modifies multimaps)   | O(min(n, m))    |
| `lower_bound()` | Returns an iterator to the first element that is **not less** than the key.       | `multimap.lower_bound(key);`     | `multimap.lower_bound(2);`       | Iterator to first element >= key | O(log n)        |
| `upper_bound()` | Returns an iterator to the first element that is **greater** than the key.        | `multimap.upper_bound(key);`     | `multimap.upper_bound(2);`       | Iterator to first element > key  | O(log n)        |
| `equal_range()` | Returns a pair of iterators to the **lower** and **upper** bounds of a key.       | `multimap.equal_range(key);`     | `multimap.equal_range(2);`       | Pair of iterators                | O(log n)        |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **1D Multimap (Key-Value Pair)**:

  ```cpp
  multimap<int, string> m;
  ```

* **2D Multimap (Map of Maps)**:

  ```cpp
  multimap<int, multimap<int, string>> m;
  ```

* **Mixed with other STL containers**:

  ```cpp
  multimap<int, unordered_set<string>> m;
  ```

#### 🔧 **Initialization Techniques**

* **Using curly braces**:

  ```cpp
  multimap<int, string> m = {{1, "apple"}, {1, "banana"}, {2, "cherry"}};
  ```

* **Using `insert()`**:

  ```cpp
  multimap<int, string> m;
  m.insert({1, "apple"});
  m.insert({1, "banana"});
  m.insert({2, "cherry"});
  ```

* **Using `emplace()`** (recommended for efficiency):

  ```cpp
  multimap<int, string> m;
  m.emplace(1, "apple");
  m.emplace(1, "banana");
  m.emplace(2, "cherry");
  ```

* **With custom data types or classes**:

  ```cpp
  struct Person {
      string name;
      int age;
      Person(string name, int age) : name(name), age(age) {}
  };

  multimap<int, Person> m;
  m[1] = Person("Alice", 25);
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                               | Example Usage                                                                         | Output                                      |
| ------------------------ | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------- |
| **Index-based loop**     | Not applicable (multimap does not support direct indexing).               | N/A                                                                                   | N/A                                         |
| **Range-based for loop** | Iterate over key-value pairs in the multimap.                             | `for (auto &pair : multimap) { cout << pair.first << " : " << pair.second << endl; }` | `1 : apple`<br>`1 : banana`<br>`2 : cherry` |
| **Iterators**            | Use iterators to access key-value pairs manually.                         | `auto it = multimap.begin(); cout << it->first << " : " << it->second;`               | `1 : apple`                                 |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability in loops. | `for (const auto& pair : multimap) { cout << pair.first << " : " << pair.second; }`   | `1 : apple`<br>`1 : banana`<br>`2 : cherry` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a list of students and their grades (with possible duplicates for the same grade), find all students who share the highest grade.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <multimap>
using namespace std;

void highestGradeStudents(const multimap<int, string>& students) {
    auto max_grade = students.rbegin()->first;
    for (auto it = students.rbegin(); it != students.rend(); ++it) {
        if (it->first == max_grade)
            cout << it->second << " ";
        else
            break;
    }
}

int main() {
    multimap<int, string> students = {{85, "Alice"}, {92, "Bob"}, {92, "Charlie"}, {78, "David"}};
    cout << "Students with the highest grade: ";
    highestGradeStudents(students);  // Output: Bob Charlie
    return 0;
}
```

#### 💡 **Output**:

```
Students with the highest grade: Bob Charlie
```

#### ⏱️ **Time Complexity**:

* **Time Complexity:** O(n) for the loop through the multimap.
* **Space Complexity:** O(n) due to storing the multimap with `n` students.
