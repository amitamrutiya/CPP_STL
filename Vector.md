## 📚 **STL: `vector` (Dynamic Array)**

### 🔍 **What It Is Used For:**

* A **dynamic array** that can grow and shrink in size.
* Stores elements in contiguous memory locations, providing fast random access.

---

### 🏅 **Where It Is Preferred and Why:**

* **Preferred when:**

  * You need fast random access to elements (constant-time `O(1)` access).
  * You expect to perform many **insertions at the end** or **dynamic resizing**.
  * The size of the container may change during runtime.
* **Why:**

  * `vector` manages memory efficiently, resizing as needed, with amortized constant time for adding elements at the end.

---

### 🌎 **Real-world or DSA Use Cases:**

* **Real-world:**

  * Used for arrays that need to resize dynamically, such as in dynamic programming or when implementing containers like lists of items in web pages.
* **DSA:**

  * Frequently used for solving problems related to arrays or dynamic lists, such as **sorting**, **searching**, **subarray problems**, or **sliding window techniques**.

---

### 🏗️ **Internal Data Structure and Behavior:**

* **Data structure:** Internally uses a **dynamic array** (resizable array).
* **Behavior:**

  * Starts with an initial size (usually small) and increases its capacity exponentially when elements exceed the current capacity (doubling).
  * It’s efficient when elements are added at the end or accessed randomly, but inserting in the middle or at the front requires shifting elements.

---

### ✔️ **Advantages and Limitations:**

#### ✅ **Advantages:**

* **Fast Random Access:** `O(1)` for access by index.
* **Efficient Insertion at End:** Amortized constant time (`O(1)`) for `push_back()`.
* **Automatic Resizing:** Can grow and shrink as needed.

#### ❌ **Limitations:**

* **Insertion/Deletion in Middle/Front:** `O(n)` as elements need to be shifted.
* **Memory Overhead:** Resizing can be expensive if the vector is large and resized frequently.

---

### 🚫 **When Not to Use It:**

* **Avoid** when you have frequent insertions/deletions at the front or middle of the container. Use a `deque` or `list` instead.
* **Avoid** if you need constant-time insertion and deletion, as `vector` isn’t ideal for that.

---

### 🧠 **Time & Space Complexities:**

| Operation                    | Time Complexity | Space Complexity |
| ---------------------------- | --------------- | ---------------- |
| **Access (by index)**        | O(1)            | O(n)             |
| **Insertion (end)**          | Amortized O(1)  | O(n)             |
| **Insertion (front/middle)** | O(n)            | O(n)             |
| **Deletion (end)**           | O(1)            | O(n)             |
| **Deletion (front/middle)**  | O(n)            | O(n)             |
| **Resize**                   | Amortized O(n)  | O(n)             |

---

### 🛠️ **Declaration Variants:**

#### Basic 1D and 2D usage:

```cpp
std::vector<int> v1;               // 1D vector of integers
std::vector<std::vector<int>> v2;  // 2D vector (vector of vectors)
```

#### Mixed with Other STL Containers:

```cpp
std::vector<std::pair<int, int>> v;  // Vector of pairs
std::vector<std::string> v;           // Vector of strings
```

#### Initialization Techniques:

```cpp
std::vector<int> v(5, 10);           // 5 elements, initialized to 10
std::vector<int> v = {1, 2, 3, 4};   // List initialization
std::vector<int> v(v1.begin(), v1.end()); // Copy initialization from another vector
```

#### With Custom Data Types or Classes:

```cpp
class Point {
public:
    int x, y;
    Point(int x, int y) : x(x), y(y) {}
};

std::vector<Point> v;  // Vector of custom objects
```

---

### 📚 **15 Important Methods for `vector`**

| Method            | Description                                                                     | Syntax                 | Example Usage                  | Output                      | Time Complexity |
| ----------------- | ------------------------------------------------------------------------------- | ---------------------- | ------------------------------ | --------------------------- | --------------- |
| `push_back()`     | Adds an element to the end of the vector                                        | `v.push_back(x);`      | `v.push_back(10);`             | No output (modifies vector) | Amortized O(1)  |
| `pop_back()`      | Removes the last element                                                        | `v.pop_back();`        | `v.pop_back();`                | No output (modifies vector) | O(1)            |
| `size()`          | Returns the number of elements in the vector                                    | `v.size();`            | `v.size();`                    | `5`                         | O(1)            |
| `capacity()`      | Returns the number of elements the vector can hold                              | `v.capacity();`        | `v.capacity();`                | `8`                         | O(1)            |
| `resize()`        | Resizes the vector to the given size                                            | `v.resize(n);`         | `v.resize(5);`                 | No output (modifies vector) | O(n)            |
| `clear()`         | Removes all elements from the vector                                            | `v.clear();`           | `v.clear();`                   | No output (modifies vector) | O(n)            |
| `front()`         | Returns a reference to the first element                                        | `v.front();`           | `v.front();`                   | `1`                         | O(1)            |
| `back()`          | Returns a reference to the last element                                         | `v.back();`            | `v.back();`                    | `4`                         | O(1)            |
| `at()`            | Accesses an element with bounds checking                                        | `v.at(i);`             | `v.at(2);`                     | `3`                         | O(1)            |
| `empty()`         | Checks if the vector is empty                                                   | `v.empty();`           | `v.empty();`                   | `false`                     | O(1)            |
| `insert()`        | Inserts an element at a specified position                                      | `v.insert(pos, val);`  | `v.insert(v.begin() + 2, 10);` | No output (modifies vector) | O(n)            |
| `erase()`         | Removes an element at a specified position                                      | `v.erase(pos);`        | `v.erase(v.begin() + 1);`      | No output (modifies vector) | O(n)            |
| `emplace_back()`  | Adds a new element to the end of the vector (more efficient than `push_back()`) | `v.emplace_back(val);` | `v.emplace_back(20);`          | No output (modifies vector) | Amortized O(1)  |
| `swap()`          | Swaps the contents of two vectors                                               | `v1.swap(v2);`         | `v1.swap(v2);`                 | No output (modifies vector) | O(1)            |
| `shrink_to_fit()` | Requests the reduction of capacity to fit the size                              | `v.shrink_to_fit();`   | `v.shrink_to_fit();`           | No output (modifies vector) | O(n)            |


---

### 🔄 **Traversal Techniques:**

#### Index-based Loop:

```cpp
for (int i = 0; i < v.size(); ++i) {
    std::cout << v[i] << " ";
}
```

#### Range-based Loop:

```cpp
for (auto &elem : v) {
    std::cout << elem << " ";
}
```

#### Iterators (Basic and Reverse):

```cpp
// Forward iterator
for (auto it = v.begin(); it != v.end(); ++it) {
    std::cout << *it << " ";
}

// Reverse iterator
for (auto it = v.rbegin(); it != v.rend(); ++it) {
    std::cout << *it << " ";
}
```

#### Using `auto`:

```cpp
for (auto &elem : v) {
    std::cout << elem << " ";
}
```

---

### 🧪 **Advanced Practice Problem:**

#### **Problem: Maximum Subarray Sum (Kadane's Algorithm)**

**Problem:** Given a vector of integers, find the **maximum sum of any contiguous subarray**.

#### **Constraints:**

* Vector size: 1 ≤ `n` ≤ 10^6
* Element values: -10^3 ≤ `A[i]` ≤ 10^3

#### **Solution:**

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int maxSubArraySum(const vector<int>& v) {
    int max_so_far = v[0], max_ending_here = v[0];
    for (size_t i = 1; i < v.size(); ++i) {
        max_ending_here = max(v[i], max_ending_here + v[i]);
        max_so_far = max(max_so_far, max_ending_here);
    }
    return max_so_far;
}

int main() {
    vector<int> v = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
    cout << "Maximum Subarray Sum: " << maxSubArraySum(v) << endl;
    return 0;
}
```

#### **Explanation:**

* **Time Complexity:** O(n), where `n` is the size of the vector.
* **Space Complexity:** O(1), since we are using a constant amount of extra space.
* **Step-by-step:** This algorithm finds the maximum sum of any subarray in a single pass by keeping track of the current subarray sum (`max_ending_here`) and the global maximum sum (`max_so_far`).

---

### ✅ **Conclusion for `vector`:**

* **Best for:** Random access, dynamic array, and efficient push\_back operations.
* **Avoid when:** You need frequent insertions/deletions in the middle or front.
