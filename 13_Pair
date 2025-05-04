## 🚀 **STL: `pair` (Utility Container for Two Elements)**

#### 🧠 **What the container is used for**:

* `pair` is a simple container in C++ that holds **two related objects** as a single unit.
* It is often used to represent key-value pairs or any two objects that are logically connected.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to store **two values** together, especially when those values are of **different types**.
  * It's commonly used in situations like storing a **key-value pair** in associative containers (like `map`, `unordered_map`) or as a return type for functions.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Frequently used for **pairing elements** in algorithms (like in sorting, graph algorithms, etc.).
* **Real-world:** Used in **key-value storage**, representing coordinates (x, y), time (start, end), or mapping between two entities (like name-age, city-country, etc.).

#### 🔧 **Internal data structure and behavior**:

* `pair` is a **template class** that holds two objects.
* The objects can be of **different types** and can be accessed using `first` and `second` members.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Simple and lightweight.
  * Useful for combining two related values into one object.
  * Supports a variety of use cases, such as returning two values from a function.
* **Limitations**:

  * Limited to holding just two elements.
  * Does not provide direct container-like behaviors (e.g., iteration).

#### 🚫 **When not to use it**:

* When you need to hold more than two elements, as `pair` can only hold two items.
* Not ideal if the two elements need complex manipulation beyond direct access.

---

### 🧠 **Time & Space Complexities for `pair`**

| Operation                 | Time Complexity | Space Complexity |
| ------------------------- | --------------- | ---------------- |
| Construction              | O(1)            | O(1)             |
| Access (via first/second) | O(1)            | O(1)             |

---

### 📚 **15 Important Methods for `pair`**

| Method         | Description                                                      | Syntax                           | Example Usage                                                                                            | Output                          | Time Complexity |
| -------------- | ---------------------------------------------------------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------- | --------------- |
| `first`        | Accesses the first element of the pair.                          | `pair.first`                     | `pair<int, string> p = {1, "Alice"}; cout << p.first;`                                                   | `1`                             | O(1)            |
| `second`       | Accesses the second element of the pair.                         | `pair.second`                    | `pair<int, string> p = {1, "Alice"}; cout << p.second;`                                                  | `Alice`                         | O(1)            |
| `make_pair()`  | Creates a pair object from two values.                           | `make_pair(a, b)`                | `auto p = make_pair(1, "Alice");`                                                                        | `pair<int, string>{1, "Alice"}` | O(1)            |
| `tie()`        | Unpacks the pair into two separate variables.                    | `tie(a, b) = p;`                 | `auto [a, b] = p;`                                                                                       | `a = 1, b = "Alice"`            | O(1)            |
| `operator==`   | Checks if two pairs are equal.                                   | `pair1 == pair2`                 | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {1, "Alice"}; cout << (p1 == p2);`          | `1 (true)`                      | O(1)            |
| `operator!=`   | Checks if two pairs are not equal.                               | `pair1 != pair2`                 | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {2, "Bob"}; cout << (p1 != p2);`            | `1 (true)`                      | O(1)            |
| `operator<`    | Compares two pairs for ordering.                                 | `pair1 < pair2`                  | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {2, "Bob"}; cout << (p1 < p2);`             | `1 (true)`                      | O(1)            |
| `operator>`    | Compares two pairs for ordering.                                 | `pair1 > pair2`                  | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {2, "Bob"}; cout << (p1 > p2);`             | `0 (false)`                     | O(1)            |
| `operator<=`   | Checks if the first pair is less than or equal to the second.    | `pair1 <= pair2`                 | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {2, "Bob"}; cout << (p1 <= p2);`            | `1 (true)`                      | O(1)            |
| `operator>=`   | Checks if the first pair is greater than or equal to the second. | `pair1 >= pair2`                 | `pair<int, string> p1 = {2, "Alice"}; pair<int, string> p2 = {1, "Bob"}; cout << (p1 >= p2);`            | `1 (true)`                      | O(1)            |
| `swap()`       | Swaps the values of two pairs.                                   | `pair1.swap(pair2)`              | `pair<int, string> p1 = {1, "Alice"}; pair<int, string> p2 = {2, "Bob"}; p1.swap(p2); cout << p1.first;` | `2`                             | O(1)            |
| `std::get<>()` | Accesses the element of a pair using index notation.             | `get<0>(pair)` or `get<1>(pair)` | `pair<int, string> p = {1, "Alice"}; cout << get<0>(p);`                                                 | `1`                             | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **Basic Pair Declaration**:

  ```cpp
  pair<int, string> p1;
  ```

* **Initialization with values**:

  ```cpp
  pair<int, string> p2 = {1, "Alice"};
  ```

* **Using `make_pair()`**:

  ```cpp
  pair<int, string> p3 = make_pair(2, "Bob");
  ```

* **With custom data types**:

  ```cpp
  struct Point {
      int x, y;
  };
  pair<Point, string> p4 = {Point{1, 2}, "Point1"};
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                           | Example Usage                                                         | Output               |
| ------------------------ | --------------------------------------------------------------------- | --------------------------------------------------------------------- | -------------------- |
| **Index-based loop**     | Not applicable directly (pairs do not support direct indexing).       | N/A                                                                   | N/A                  |
| **Range-based for loop** | Iterate over pairs in a container (e.g., vector of pairs).            | `for (auto &p : vec) { cout << p.first << " " << p.second << endl; }` | `1 Alice`<br>`2 Bob` |
| **Iterators**            | Use iterators to access pairs in containers like `vector<pair<...>>`. | `auto it = vec.begin(); cout << it->first << " " << it->second;`      | `1 Alice`            |
| **auto & const auto**    | Use `auto` for type inference and `const auto` for immutability.      | `for (const auto& p : vec) { cout << p.first << " " << p.second; }`   | `1 Alice`<br>`2 Bob` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a set of **pairs of student names and their grades**, sort the students by their grades in descending order and output the result.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <utility>
using namespace std;

int main() {
    vector<pair<string, int>> students = {{"Alice", 90}, {"Bob", 85}, {"Charlie", 95}};
    
    // Sorting pairs by second element (grade) in descending order
    sort(students.begin(), students.end(), [](const pair<string, int>& a, const pair<string, int>& b) {
        return a.second > b.second;
    });
    
    // Printing sorted students
    for (auto &student : students) {
        cout << student.first << ": " << student.second << endl;
    }
    
    return 0;
}
```

#### 💡 **Output**:

```
Charlie: 95
Alice: 90
Bob: 85
```

#### ⏱️ **Time Complexity**:

* Sorting: O(n log n)
* Traversing the vector: O(n)
