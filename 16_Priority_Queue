## 🚀 **STL: `priority_queue` (Max-Heap by Default)**

#### 🧠 **What the container is used for**:

* **`priority_queue`** is a container adapter that provides constant-time access to the **largest element** (in the default max-heap configuration).
* It is used when you need to keep elements in a collection, but access the largest (or smallest) element efficiently.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to **quickly access** the largest (or smallest) element.
  * Used in scenarios like **sorting**, **heap-based algorithms**, and **priority scheduling**.

#### 🌍 **Real-world or DSA use cases**:

* **Real-world:** Task scheduling systems where tasks have priorities, dynamic event handling, real-time systems.
* **DSA:** Problems like **Dijkstra’s algorithm**, **K-th largest element**, **Huffman coding**.

#### 🔧 **Internal data structure and behavior**:

* `priority_queue` is typically implemented as a **max-heap** (default) or **min-heap** (if specified).
* It ensures that the **largest element** is always at the top of the queue and can be accessed in constant time.
* Insertions take logarithmic time, and removals take logarithmic time as well due to heap restructuring.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Efficiently supports access to the largest (or smallest) element.
  * Ideal for scenarios requiring **priority-based processing**.
* **Limitations**:

  * No access to arbitrary elements (cannot directly access other elements besides the top).
  * Does not allow efficient arbitrary removals.

#### 🚫 **When not to use it**:

* When you need to access arbitrary elements in the collection (e.g., in a set or list).
* When priority-based removal is not required.

---

### 🧠 **Time & Space Complexities for `priority_queue`**

| Operation        | Time Complexity | Space Complexity |
| ---------------- | --------------- | ---------------- |
| Construction     | O(1)            | O(n)             |
| Push (insert)    | O(log n)        | O(n)             |
| Pop (remove)     | O(log n)        | O(n)             |
| Top (access max) | O(1)            | O(1)             |
| Empty            | O(1)            | O(1)             |
| Size             | O(1)            | O(1)             |

---

### 📚 **15 Important Methods for `priority_queue`**

| Method    | Description                                       | Syntax       | Example Usage         | Output      | Time Complexity |
| --------- | ------------------------------------------------- | ------------ | --------------------- | ----------- | --------------- |
| `push()`  | Adds an element to the priority queue.            | `pq.push(x)` | `pq.push(10);`        | (No output) | O(log n)        |
| `pop()`   | Removes the top (largest) element from the queue. | `pq.pop()`   | `pq.pop();`           | (No output) | O(log n)        |
| `top()`   | Returns the top (largest) element.                | `pq.top()`   | `cout << pq.top();`   | `10`        | O(1)            |
| `empty()` | Checks if the priority queue is empty.            | `pq.empty()` | `cout << pq.empty();` | `0 (false)` | O(1)            |
| `size()`  | Returns the number of elements in the queue.      | `pq.size()`  | `cout << pq.size();`  | `1`         | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **Basic Priority Queue Declaration**:

  ```cpp
  priority_queue<int> pq;
  ```

* **With elements (max-heap)**:

  ```cpp
  priority_queue<int> pq = {10, 20, 30};
  ```

* **With custom comparator (min-heap)**:

  ```cpp
  priority_queue<int, vector<int>, greater<int>> pq;
  pq.push(10);
  pq.push(20);
  pq.push(5);
  ```

* **With custom data types (using a comparator)**:

  ```cpp
  struct Task {
      int priority;
      string description;
  };

  struct CompareTask {
      bool operator()(const Task& a, const Task& b) {
          return a.priority < b.priority;  // max-heap
      }
  };

  priority_queue<Task, vector<Task>, CompareTask> pq;
  pq.push(Task{1, "Task 1"});
  pq.push(Task{2, "Task 2"});
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                         | Example Usage | Output |
| ------------------------ | ------------------------------------------------------------------- | ------------- | ------ |
| **Index-based loop**     | Not applicable (priority\_queue does not allow direct indexing).    | N/A           | N/A    |
| **Range-based for loop** | Not applicable (priority\_queue does not provide direct iteration). | N/A           | N/A    |
| **Iterators**            | Not applicable (priority\_queue does not provide iterators).        | N/A           | N/A    |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Find the **Kth largest element** in an array using a priority queue.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

int findKthLargest(vector<int>& nums, int k) {
    priority_queue<int> pq;
    for (int num : nums) {
        pq.push(num);
    }
    
    for (int i = 1; i < k; i++) {
        pq.pop();  // Pop the top element (largest)
    }
    
    return pq.top();  // Return the Kth largest element
}

int main() {
    vector<int> nums = {3, 2, 1, 5, 6, 4};
    int k = 2;
    cout << "The " << k << "th largest element is " << findKthLargest(nums, k) << endl;
    return 0;
}
```

#### 💡 **Output**:

```
The 2th largest element is 5
```

#### ⏱️ **Time Complexity**:

* Inserting all elements: O(n log n)
* Finding the Kth largest: O(k log n)
* Total: O(n log n)

#### 🏋️‍♂️ **Space Complexity**:

* O(n), as we store all elements in the priority queue.
