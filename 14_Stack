## 🚀 **STL: `stack` (LIFO Container)**

#### 🧠 **What the container is used for**:

* **`stack`** is a **container adapter** that operates in a **Last-In, First-Out (LIFO)** manner.
* It is used for managing a collection of elements where the last inserted element is accessed first, which makes it ideal for algorithms like **backtracking**, **depth-first search (DFS)**, and managing function calls.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to access elements in reverse order (the most recently added element is processed first).
  * It provides simple operations like **push**, **pop**, and **top**.

#### 🌍 **Real-world or DSA use cases**:

* **Real-world:** Managing function calls in recursion or expression evaluation (e.g., balancing parentheses).
* **DSA:** Implemented in **depth-first search** (DFS) or any problem requiring backtracking (e.g., maze-solving).

#### 🔧 **Internal data structure and behavior**:

* Internally, `stack` is typically implemented using **`deque`** or **`vector`**, but it can only access elements through the top.
* It doesn't allow random access, meaning you can only work with the **top element**.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Simple interface for **LIFO** operations.
  * Efficient for problems that need to track the most recent element.
* **Limitations**:

  * Does not provide access to the underlying container (no random access).
  * Can only access the **top element**; no middle or bottom access.

#### 🚫 **When not to use it**:

* When you need to access multiple elements at once.
* If random access or middle element manipulation is required.

---

### 🧠 **Time & Space Complexities for `stack`**

| Operation    | Time Complexity | Space Complexity |
| ------------ | --------------- | ---------------- |
| Construction | O(1)            | O(1)             |
| Push         | O(1)            | O(1)             |
| Pop          | O(1)            | O(1)             |
| Top          | O(1)            | O(1)             |
| Empty        | O(1)            | O(1)             |
| Size         | O(1)            | O(1)             |

---

### 📚 **15 Important Methods for `stack`**

| Method    | Description                                  | Syntax                | Example Usage               | Output      | Time Complexity |
| --------- | -------------------------------------------- | --------------------- | --------------------------- | ----------- | --------------- |
| `push()`  | Adds an element to the top of the stack.     | `stack.push(x)`       | `stack<int> s; s.push(10);` | (No output) | O(1)            |
| `pop()`   | Removes the top element from the stack.      | `stack.pop()`         | `s.pop();`                  | (No output) | O(1)            |
| `top()`   | Returns the top element of the stack.        | `stack.top()`         | `cout << s.top();`          | `10`        | O(1)            |
| `empty()` | Checks if the stack is empty.                | `stack.empty()`       | `cout << s.empty();`        | `0 (false)` | O(1)            |
| `size()`  | Returns the number of elements in the stack. | `stack.size()`        | `cout << s.size();`         | `1`         | O(1)            |
| `swap()`  | Swaps the content of two stacks.             | `stack1.swap(stack2)` | `s1.swap(s2);`              | (No output) | O(1)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **Basic Stack Declaration**:

  ```cpp
  stack<int> s;
  ```

* **With elements**:

  ```cpp
  stack<int> s = {10, 20, 30};
  ```

* **Using `push()`**:

  ```cpp
  stack<string> s;
  s.push("Hello");
  s.push("World");
  ```

* **With custom data types**:

  ```cpp
  struct Point {
      int x, y;
  };
  stack<Point> s;
  s.push(Point{1, 2});
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                           | Example Usage | Output |
| ------------------------ | --------------------------------------------------------------------- | ------------- | ------ |
| **Index-based loop**     | Not applicable directly (stacks do not support direct indexing).      | N/A           | N/A    |
| **Range-based for loop** | Not applicable (cannot directly access elements in stack except top). | N/A           | N/A    |
| **Iterators**            | Not applicable (stack does not provide iterators).                    | N/A           | N/A    |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Implement a function to **reverse a string** using a stack. The function will take a string as input and return its reverse by pushing characters onto a stack and popping them in reverse order.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

string reverseString(const string& str) {
    stack<char> s;
    
    // Push all characters of the string onto the stack
    for (char ch : str) {
        s.push(ch);
    }
    
    string reversed = "";
    
    // Pop characters from the stack to get the reversed string
    while (!s.empty()) {
        reversed += s.top();
        s.pop();
    }
    
    return reversed;
}

int main() {
    string input = "Hello, World!";
    cout << "Reversed string: " << reverseString(input) << endl;
    return 0;
}
```

#### 💡 **Output**:

```
Reversed string: !dlroW ,olleH
```

#### ⏱️ **Time Complexity**:

* Pushing each character onto the stack: O(n)
* Popping each character from the stack: O(n)
* Total: O(n)

#### 🏋️‍♂️ **Space Complexity**:

* O(n), since we are using a stack to store all characters of the string.
