## 🚀 **STL: `list` (Doubly Linked List)**

#### 🧠 **What the container is used for**:

* A `list` is a **doubly linked list** that allows efficient insertions and deletions at both ends and in the middle of the container.

#### 📍 **Where it is preferred and why**:

* Ideal for scenarios that require frequent insertions and deletions at arbitrary positions without needing to access elements via indices.
* Preferred when performance for insertion and deletion is critical.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Useful for problems involving frequent insertions or deletions, such as in queue, deque, or cache implementations.
* **Real-world:** Used in many applications like music playlists, browser history, and undo mechanisms in editors.

#### 🔧 **Internal data structure and behavior**:

* The `list` is implemented as a doubly linked list, where each element points to both the next and previous elements.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Constant time insertions and deletions at both ends and at any position.
  * Can be more efficient than a vector when modifying the container often.
* **Limitations**:

  * Slower random access compared to `vector` (O(n) for accessing an element at a specific position).
  * Higher memory overhead due to storing two pointers per element (next and prev).

#### 🚫 **When not to use it**:

* Avoid using `list` when you need fast random access to elements.
* If you only need efficient push/pop operations at the end of the container, a `deque` or `vector` may be better.

---

### 🧠 **Time & Space Complexities for `list`**

| Operation             | Time Complexity | Space Complexity |
| --------------------- | --------------- | ---------------- |
| Insertion (begin/end) | O(1)            | O(1)             |
| Insertion (middle)    | O(n)            | O(1)             |
| Deletion (begin/end)  | O(1)            | O(1)             |
| Deletion (middle)     | O(n)            | O(1)             |
| Access                | O(n)            | O(1)             |
| Search                | O(n)            | O(1)             |

---

### 📚 **15 Important Methods for `list`**

| Method         | Description                                       | Syntax                | Example Usage              | Output                     | Time Complexity |
| -------------- | ------------------------------------------------- | --------------------- | -------------------------- | -------------------------- | --------------- |
| `push_back()`  | Adds an element to the end of the list            | `l.push_back(x);`     | `l.push_back(10);`         | No output (modifies list)  | O(1)            |
| `push_front()` | Adds an element to the front of the list          | `l.push_front(x);`    | `l.push_front(5);`         | No output (modifies list)  | O(1)            |
| `pop_back()`   | Removes the last element from the list            | `l.pop_back();`       | `l.pop_back();`            | No output (modifies list)  | O(1)            |
| `pop_front()`  | Removes the first element from the list           | `l.pop_front();`      | `l.pop_front();`           | No output (modifies list)  | O(1)            |
| `size()`       | Returns the number of elements in the list        | `l.size();`           | `l.size();`                | `3`                        | O(1)            |
| `empty()`      | Checks if the list is empty                       | `l.empty();`          | `l.empty();`               | `false`                    | O(1)            |
| `front()`      | Returns a reference to the first element          | `l.front();`          | `l.front();`               | `5`                        | O(1)            |
| `back()`       | Returns a reference to the last element           | `l.back();`           | `l.back();`                | `10`                       | O(1)            |
| `insert()`     | Inserts an element at a specified position        | `l.insert(pos, val);` | `l.insert(l.begin(), 20);` | No output (modifies list)  | O(n)            |
| `erase()`      | Removes an element at a specified position        | `l.erase(pos);`       | `l.erase(l.begin());`      | No output (modifies list)  | O(n)            |
| `clear()`      | Removes all elements from the list                | `l.clear();`          | `l.clear();`               | No output (modifies list)  | O(n)            |
| `remove()`     | Removes all occurrences of a specific element     | `l.remove(val);`      | `l.remove(10);`            | No output (modifies list)  | O(n)            |
| `splice()`     | Transfers elements from another list to this list | `l.splice(pos, l2);`  | `l.splice(l.begin(), l2);` | No output (modifies lists) | O(1)            |
| `merge()`      | Merges two sorted lists                           | `l.merge(l2);`        | `l.merge(l2);`             | No output (modifies list)  | O(n)            |
| `sort()`       | Sorts the elements of the list                    | `l.sort();`           | `l.sort();`                | No output (modifies list)  | O(n log n)      |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                              | Output                    |
| ------------------------ | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------- |
| **Index-based loop**     | Using iterators to access elements by index.                                    | `for (auto it = l.begin(); it != l.end(); ++it) { cout << *it << " "; }`   | `5 10`                    |
| **Range-based for loop** | A simple loop to iterate over the list elements.                                | `for (auto &val : l) { cout << val << " "; }`                              | `5 10`                    |
| **Iterators**            | Using iterators to manually navigate through the list.                          | `auto it = l.begin(); cout << *it;`                                        | `5`                       |
| **Reverse Iterators**    | Using reverse iterators to iterate backward.                                    | `for (auto it = l.rbegin(); it != l.rend(); ++it) { cout << *it << " "; }` | `10 5`                    |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (auto &val : l) { val *= 2; }`                                        | No output (modifies list) |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a list of numbers, you need to perform the following operations:

1. Insert a number at the front of the list.
2. Remove all occurrences of a number.
3. Sort the list and output the result.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    // Create a list and perform operations
    list<int> l = {10, 20, 30, 40, 50};

    // 1. Insert 5 at the front of the list
    l.push_front(5);

    // 2. Remove all occurrences of 20
    l.remove(20);

    // 3. Sort the list
    l.sort();

    // Output the sorted list
    for (const auto& val : l) {
        cout << val << " ";
    }

    return 0;
}
```

#### 💡 **Output**:

```
5 10 30 40 50
```

#### ⏱️ **Time Complexity**:

* **Insertion**: O(1) at the front.
* **Removal**: O(n) for removing all occurrences.
* **Sorting**: O(n log n).
