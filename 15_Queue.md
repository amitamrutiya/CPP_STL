## 🚀 **STL: `queue` (FIFO Container)**

#### 🧠 **What the container is used for**:

* **`queue`** is a **container adapter** that operates in a **First-In, First-Out (FIFO)** manner.
* It is used for managing elements where the **first inserted element** is processed first. Ideal for situations that need to process elements in the same order they arrive, such as task scheduling or handling requests.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to process elements in the order they arrive.
  * It is used for problems like **Breadth-First Search (BFS)** or any **scheduling** problems.

#### 🌍 **Real-world or DSA use cases**:

* **Real-world:** Print job queues, task scheduling in operating systems, handling customer requests.
* **DSA:** **Breadth-First Search (BFS)** in graph traversal, simulating real-world queue systems like customer service lines.

#### 🔧 **Internal data structure and behavior**:

* Internally, `queue` is often implemented using **`deque`** or **`list`**, allowing efficient enqueue (insertion at the back) and dequeue (removal from the front) operations.
* It provides access to only the front and back elements and operates on a FIFO principle.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Simple FIFO interface.
  * Efficient for problems that require the processing of elements in the same order they are inserted.
* **Limitations**:

  * No random access (can only access front and back).
  * No middle or bottom access to elements.

#### 🚫 **When not to use it**:

* When you need to access elements other than the front or back.
* If random access or middle element manipulation is required.

---

### 🧠 **Time & Space Complexities for `queue`**

| Operation      | Time Complexity | Space Complexity |
| -------------- | --------------- | ---------------- |
| Construction   | O(1)            | O(1)             |
| Push (enqueue) | O(1)            | O(1)             |
| Pop (dequeue)  | O(1)            | O(1)             |
| Front          | O(1)            | O(1)             |
| Back           | O(1)            | O(1)             |
| Empty          | O(1)            | O(1)             |
| Size           | O(1)            | O(1)             |

---

### 📚 **15 Important Methods for `queue`**

| Method    | Description                                      | Syntax          | Example Usage               | Output      | Time Complexity |
| --------- | ------------------------------------------------ | --------------- | --------------------------- | ----------- | --------------- |
| `push()`  | Adds an element to the back of the queue.        | `queue.push(x)` | `queue<int> q; q.push(10);` | (No output) | O(1)            |
| `pop()`   | Removes the element from the front of the queue. | `queue.pop()`   | `q.pop();`                  | (No output) | O(1)            |
| `front()` | Returns the element at the front of the queue.   | `queue.front()` | `cout << q.front();`        | `10`        | O(1)            |
| `back()`  | Returns the element at the back of the queue.    | `queue.back()`  | `cout << q.back();`         | `10`        | O(1)            |
| `empty()` | Checks if the queue is empty.                    | `queue.empty()` | `cout << q.empty();`        | `0 (false)` | O(1)            |
| `size()`  | Returns the number of elements in the queue.     | `queue.size()`  | `cout << q.size();`         | `1`         | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **Basic Queue Declaration**:

  ```cpp
  queue<int> q;
  ```

* **With elements**:

  ```cpp
  queue<int> q = {10, 20, 30};
  ```

* **Using `push()`**:

  ```cpp
  queue<string> q;
  q.push("Hello");
  q.push("World");
  ```

* **With custom data types**:

  ```cpp
  struct Task {
      int id;
      string description;
  };
  queue<Task> q;
  q.push(Task{1, "Task 1"});
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                  | Example Usage | Output |
| ------------------------ | ---------------------------------------------------------------------------- | ------------- | ------ |
| **Index-based loop**     | Not applicable directly (queues do not support direct indexing).             | N/A           | N/A    |
| **Range-based for loop** | Not applicable (cannot directly access elements in queue except front/back). | N/A           | N/A    |
| **Iterators**            | Not applicable (queue does not provide iterators).                           | N/A           | N/A    |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Implement a **task scheduler** using a queue. The function will accept a list of tasks, and you need to simulate processing these tasks in a **First-In, First-Out (FIFO)** manner.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <queue>
#include <string>
using namespace std;

void taskScheduler(queue<string>& tasks) {
    while (!tasks.empty()) {
        cout << "Processing task: " << tasks.front() << endl;
        tasks.pop();
    }
}

int main() {
    queue<string> tasks;
    tasks.push("Task 1");
    tasks.push("Task 2");
    tasks.push("Task 3");
    
    taskScheduler(tasks);
    return 0;
}
```

#### 💡 **Output**:

```
Processing task: Task 1
Processing task: Task 2
Processing task: Task 3
```

#### ⏱️ **Time Complexity**:

* Pushing each task onto the queue: O(1)
* Popping each task from the queue: O(1)
* Total: O(n)

#### 🏋️‍♂️ **Space Complexity**:

* O(n), since we are using a queue to store tasks.
