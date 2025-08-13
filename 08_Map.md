## 🚀 **STL: `map` (Associative Container for Key-Value Pairs)**

#### 🧠 **What the container is used for**:

* A `map` is an **associative container** that stores elements in **key-value** pairs, where each key is unique.
* It provides efficient **lookup**, **insertion**, and **deletion** operations based on keys.
* The elements in a `map` are always **sorted by their keys**.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store key-value pairs and need fast access or modification based on the key.
  * You require the keys to be **sorted** automatically.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Often used in problems involving frequency counts (e.g., counting character frequencies), mapping relationships between items, or storing sorted data with efficient lookup.
* **Real-world:** Useful for applications like implementing dictionaries, databases, caching systems, or building inverted indexes for search engines.

#### 🔧 **Internal data structure and behavior**:

* A `map` is typically implemented as a **self-balancing binary search tree** (e.g., **Red-Black Tree**).
* This structure ensures that elements are always sorted and provides **logarithmic time complexity** for operations like search, insertion, and deletion.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * **Sorted keys**: Elements are stored in ascending order of the keys.
  * Provides **O(log n)** time complexity for search, insertion, and deletion.
  * **Key uniqueness**: Automatically handles unique keys.
* **Limitations**:

  * **Slower than unordered containers** like `unordered_map` in terms of insertion and lookup time (O(log n) vs. O(1)).
  * Requires more memory due to the tree structure.

#### 🚫 **When not to use it**:

* Avoid `map` if you need to store unordered key-value pairs and are focused on **speed** (in this case, `unordered_map` may be a better option).
* If **memory** consumption is a concern, using `unordered_map` might be more efficient.

---

### 🧠 **Time & Space Complexities for `map`**

| Operation     | Time Complexity | Space Complexity |
| ------------- | --------------- | ---------------- |
| Insertion     | O(log n)        | O(log n)         |
| Deletion      | O(log n)        | O(log n)         |
| Access/Search | O(log n)        | O(log n)         |
| Iteration     | O(n)            | O(n)             |

---

### 📚 **15 Important Methods for `map`**

| Method          | Description                                                                       | Syntax                      | Example Usage               | Output                           | Time Complexity |
| --------------- | --------------------------------------------------------------------------------- | --------------------------- | --------------------------- | -------------------------------- | --------------- |
| `insert()`      | Inserts a key-value pair into the map.                                            | `map.insert({key, value});` | `map.insert({1, "apple"});` | No output (modifies map)         | O(log n)        |
| `erase()`       | Removes a key-value pair from the map.                                            | `map.erase(key);`           | `map.erase(1);`             | No output (modifies map)         | O(log n)        |
| `find()`        | Finds an element by its key.                                                      | `map.find(key);`            | `map.find(1);`              | Iterator or end iterator         | O(log n)        |
| `count()`       | Returns the number of elements with the specified key (always 0 or 1).            | `map.count(key);`           | `map.count(1);`             | `1` (if found)                   | O(log n)        |
| `empty()`       | Checks if the map is empty.                                                       | `map.empty();`              | `map.empty();`              | `false`                          | O(1)            |
| `size()`        | Returns the number of elements in the map.                                        | `map.size();`               | `map.size();`               | `1`                              | O(1)            |
| `clear()`       | Removes all elements from the map.                                                | `map.clear();`              | `map.clear();`              | No output (modifies map)         | O(n)            |
| `begin()`       | Returns an iterator to the first element.                                         | `map.begin();`              | `map.begin();`              | Iterator to first element        | O(1)            |
| `end()`         | Returns an iterator to the past-the-end element.                                  | `map.end();`                | `map.end();`                | Iterator past last element       | O(1)            |
| `at()`          | Accesses the value associated with a key.                                         | `map.at(key);`              | `map.at(1);`                | `"apple"`                        | O(log n)        |
| `operator[]`    | Accesses the value associated with a key (creates a new key if it doesn't exist). | `map[key]`                  | `map[2] = "banana";`        | `"banana"`                       | O(log n)        |
| `swap()`        | Swaps the contents of two maps.                                                   | `map.swap(other);`          | `map.swap(other);`          | No output (modifies maps)        | O(min(n, m))    |
| `lower_bound()` | Returns an iterator to the first element that is **not less** than the key.       | `map.lower_bound(key);`     | `map.lower_bound(2);`       | Iterator to first element >= key | O(log n)        |
| `upper_bound()` | Returns an iterator to the first element that is **greater** than the key.        | `map.upper_bound(key);`     | `map.upper_bound(2);`       | Iterator to first element > key  | O(log n)        |
| `equal_range()` | Returns a pair of iterators to the **lower** and **upper** bounds of a key.       | `map.equal_range(key);`     | `map.equal_range(2);`       | Pair of iterators                | O(log n)        |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **1D Map (Key-Value Pair)**:

  ```cpp
  map<int, string> m;
  ```

* **2D Map (Map of Maps)**:

  ```cpp
  map<int, map<int, string>> m;
  ```

* **Mixed with other STL containers**:

  ```cpp
  map<int, unordered_set<string>> m;
  ```

#### 🔧 **Initialization Techniques**

* **Using curly braces**:

  ```cpp
  map<int, string> m = {{1, "apple"}, {2, "banana"}};
  ```

* **Using `insert()`**:

  ```cpp
  map<int, string> m;
  m.insert({1, "apple"});
  m.insert({2, "banana"});
  ```

* **Using `emplace()`** (recommended for efficiency):

  ```cpp
  map<int, string> m;
  m.emplace(1, "apple");
  m.emplace(2, "banana");
  ```

* **With custom data types or classes**:

  ```cpp
  struct Person {
      string name;
      int age;
      Person(string name, int age) : name(name), age(age) {}
  };

  map<int, Person> m;
  m[1] = Person("Alice", 25);
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                               | Example Usage                                                                    | Output                      |
| ------------------------ | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | --------------------------- |
| **Index-based loop**     | Not applicable (map does not support direct indexing).                    | N/A                                                                              | N/A                         |
| **Range-based for loop** | Iterate over key-value pairs in the map.                                  | `for (auto &pair : map) { cout << pair.first << " : " << pair.second << endl; }` | `1 : apple`<br>`2 : banana` |
| **Iterators**            | Use iterators to access key-value pairs manually.                         | `auto it = map.begin(); cout << it->first << " : " << it->second;`               | `1 : apple`                 |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability in loops. | `for (const auto& pair : map) { cout << pair.first << " : " << pair.second; }`   | `1 : apple`<br>`2 : banana` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a list of students and their grades, find the student with the highest grade. Use a `map` to store the student names and their corresponding grades.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <map>
using namespace std;

string highestGradeStudent(const map<string, int>& students) {
    auto it = students.begin();
    string highestGradeStudent = it->first;
    int highestGrade = it->second;
    
    for (auto& student : students) {
        if (student.second > highestGrade) {
            highestGradeStudent = student.first;
            highestGrade = student.second;
        }
    }
    
    return highestGradeStudent;
}

int main() {
    map<string, int> students = {{"Alice", 85}, {"Bob", 92}, {"Charlie", 78}};
    cout << "Highest grade student: " << highestGradeStudent(students) << endl;  // Output: Bob
    return 0;
}
```

#### 💡 **Output**:

```
Highest grade student: Bob
```

#### ⏱️ **Time Complexity**:

* **Time Complexity:** O(n) for the loop through the map (since the map operations like find or insertion are O(log n)).
* **Space Complexity:** O(n) due to storing the map with `n` students.
