## 🚀 **STL: `deque` (Double-Ended Queue)**

#### 🧠 **What the container is used for**:

* A `deque` is a **double-ended queue**, allowing fast insertion and deletion at both the front and the back of the container.

#### 📍 **Where it is preferred and why**:

* Ideal for scenarios that require efficient operations at both ends of the container.
* Preferred when you need fast access and modification at both ends, but don't need the random access provided by `vector`.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Useful in problems like sliding window, where we need to efficiently add/remove elements from both ends.
* **Real-world:** Used in job scheduling, memory buffers, and cache implementations where data is processed in both directions.

#### 🔧 **Internal data structure and behavior**:

* Internally implemented as a dynamic array of arrays or a circular buffer, where both ends can be resized efficiently.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * O(1) time complexity for both push and pop operations at the front and back.
  * More flexible than `vector` when elements need to be accessed or modified from both ends.
* **Limitations**:

  * Slower random access compared to `vector` (O(n) for accessing an element at a specific position).
  * Higher memory overhead compared to `vector` due to internal array management.

#### 🚫 **When not to use it**:

* Avoid using `deque` when you need fast random access to elements, as `vector` or `array` would perform better.
* If you only need fast operations at one end, a `vector` or `list` might be more efficient.

---

### 🧠 **Time & Space Complexities for `deque`**

| Operation              | Time Complexity | Space Complexity |
| ---------------------- | --------------- | ---------------- |
| Insertion (front/back) | O(1)            | O(1)             |
| Deletion (front/back)  | O(1)            | O(1)             |
| Access                 | O(n)            | O(1)             |
| Search                 | O(n)            | O(1)             |

---

### 📚 **15 Important Methods for `deque`**

| Method            | Description                                         | Syntax                | Example Usage              | Output                     | Time Complexity |
| ----------------- | --------------------------------------------------- | --------------------- | -------------------------- | -------------------------- | --------------- |
| `push_back()`     | Adds an element to the back of the deque            | `d.push_back(x);`     | `d.push_back(10);`         | No output (modifies deque) | O(1)            |
| `push_front()`    | Adds an element to the front of the deque           | `d.push_front(x);`    | `d.push_front(5);`         | No output (modifies deque) | O(1)            |
| `pop_back()`      | Removes the last element from the deque             | `d.pop_back();`       | `d.pop_back();`            | No output (modifies deque) | O(1)            |
| `pop_front()`     | Removes the first element from the deque            | `d.pop_front();`      | `d.pop_front();`           | No output (modifies deque) | O(1)            |
| `size()`          | Returns the number of elements in the deque         | `d.size();`           | `d.size();`                | `3`                        | O(1)            |
| `empty()`         | Checks if the deque is empty                        | `d.empty();`          | `d.empty();`               | `false`                    | O(1)            |
| `front()`         | Returns a reference to the first element            | `d.front();`          | `d.front();`               | `5`                        | O(1)            |
| `back()`          | Returns a reference to the last element             | `d.back();`           | `d.back();`                | `10`                       | O(1)            |
| `insert()`        | Inserts an element at a specified position          | `d.insert(pos, val);` | `d.insert(d.begin(), 20);` | No output (modifies deque) | O(n)            |
| `erase()`         | Removes an element at a specified position          | `d.erase(pos);`       | `d.erase(d.begin());`      | No output (modifies deque) | O(n)            |
| `clear()`         | Removes all elements from the deque                 | `d.clear();`          | `d.clear();`               | No output (modifies deque) | O(n)            |
| `emplace_back()`  | Constructs an element in place at the back          | `d.emplace_back(x);`  | `d.emplace_back(30);`      | No output (modifies deque) | O(1)            |
| `emplace_front()` | Constructs an element in place at the front         | `d.emplace_front(x);` | `d.emplace_front(1);`      | No output (modifies deque) | O(1)            |
| `resize()`        | Resizes the deque to a specified number of elements | `d.resize(n);`        | `d.resize(5);`             | No output (modifies deque) | O(n)            |
| `swap()`          | Swaps the content of two deques                     | `d.swap(d2);`         | `d.swap(d2);`              | No output (modifies deque) | O(1)            |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                              | Output                     |
| ------------------------ | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------- |
| **Index-based loop**     | Using iterators to access elements by index.                                    | `for (auto it = d.begin(); it != d.end(); ++it) { cout << *it << " "; }`   | `5 10`                     |
| **Range-based for loop** | A simple loop to iterate over the deque elements.                               | `for (auto &val : d) { cout << val << " "; }`                              | `5 10`                     |
| **Iterators**            | Using iterators to manually navigate through the deque.                         | `auto it = d.begin(); cout << *it;`                                        | `5`                        |
| **Reverse Iterators**    | Using reverse iterators to iterate backward.                                    | `for (auto it = d.rbegin(); it != d.rend(); ++it) { cout << *it << " "; }` | `10 5`                     |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (auto &val : d) { val *= 2; }`                                        | No output (modifies deque) |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a deque of integers, you need to perform the following operations:

1. Insert an element at both the front and the back.
2. Remove an element from the front and back.
3. Sort the deque and output the result.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <deque>
#include <algorithm>
using namespace std;

int main() {
    // Create a deque and perform operations
    deque<int> d = {10, 20, 30, 40};

    // 1. Insert 5 at the front and 50 at the back
    d.push_front(5);
    d.push_back(50);

    // 2. Remove an element from the front and back
    d.pop_front();
    d.pop_back();

    // 3. Sort the deque
    sort(d.begin(), d.end());

    // Output the sorted deque
    for (const auto& val : d) {
        cout << val << " ";
    }

    return 0;
}
```

#### 💡 **Output**:

```
10 20 30 40
```

#### ⏱️ **Time Complexity**:

* **Insertion (front/back)**: O(1).
* **Removal (front/back)**: O(1).
* **Sorting**: O(n log n).
