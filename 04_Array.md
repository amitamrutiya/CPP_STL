## 🚀 **STL: `array` (Fixed-size Array)**

#### 🧠 **What the container is used for**:

* `array` is a **fixed-size container** that wraps a C-style array.
* It provides array-like functionality with added safety, such as bounds checking, while maintaining the speed of a native array.

#### 📍 **Where it is preferred and why**:

* Preferred when the size of the container is known at compile time and will not change during runtime.
* It allows access to elements like a regular array, but with additional methods for safe and convenient use.

#### 🌍 **Real-world or DSA use cases**:

* **DSA:** Useful for problems where array sizes are known and fixed ahead of time.
* **Real-world:** Common in systems where array sizes are fixed, like embedded systems, buffers, or static memory management.

#### 🔧 **Internal data structure and behavior**:

* Internally, it is backed by a regular C-style array, but with extra features provided by the `std::array` class.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Allows all the benefits of C-style arrays (fast element access).
  * Bounds checking on access through `.at()`.
  * Safer and more flexible than raw arrays.
* **Limitations**:

  * Fixed size, which means you cannot resize it at runtime.
  * Not as flexible as other containers like `vector` if you need dynamic resizing.

#### 🚫 **When not to use it**:

* Avoid using `array` if the container size needs to change during runtime.
* If you need resizing or dynamic memory allocation, consider using other containers like `vector`.

---

### 🧠 **Time & Space Complexities for `array`**

| Operation              | Time Complexity | Space Complexity |
| ---------------------- | --------------- | ---------------- |
| Insertion (front/back) | O(1)            | O(1)             |
| Deletion (front/back)  | O(1)            | O(1)             |
| Access                 | O(1)            | O(1)             |
| Search                 | O(n)            | O(1)             |

---

### 📚 **15 Important Methods for `array`**

| Method       | Description                                           | Syntax             | Example Usage      | Output                                  | Time Complexity |
| ------------ | ----------------------------------------------------- | ------------------ | ------------------ | --------------------------------------- | --------------- |
| `at()`       | Accesses an element with bounds checking              | `arr.at(i);`       | `arr.at(2);`       | `3`                                     | O(1)            |
| `front()`    | Returns the first element of the array                | `arr.front();`     | `arr.front();`     | `1`                                     | O(1)            |
| `back()`     | Returns the last element of the array                 | `arr.back();`      | `arr.back();`      | `5`                                     | O(1)            |
| `fill()`     | Assigns a value to all elements in the array          | `arr.fill(x);`     | `arr.fill(10);`    | No output (modifies array)              | O(n)            |
| `size()`     | Returns the number of elements in the array           | `arr.size();`      | `arr.size();`      | `5`                                     | O(1)            |
| `empty()`    | Checks if the array is empty                          | `arr.empty();`     | `arr.empty();`     | `false`                                 | O(1)            |
| `data()`     | Returns a pointer to the underlying data of the array | `arr.data();`      | `arr.data();`      | Pointer to array data                   | O(1)            |
| `swap()`     | Swaps the contents of two arrays                      | `arr.swap(other);` | `arr.swap(other);` | No output (modifies array)              | O(1)            |
| `begin()`    | Returns an iterator to the first element              | `arr.begin();`     | `arr.begin();`     | Iterator pointing to first element      | O(1)            |
| `end()`      | Returns an iterator to the past-the-end element       | `arr.end();`       | `arr.end();`       | Iterator past the last element          | O(1)            |
| `rbegin()`   | Returns a reverse iterator to the last element        | `arr.rbegin();`    | `arr.rbegin();`    | Reverse iterator                        | O(1)            |
| `rend()`     | Returns a reverse iterator past the first element     | `arr.rend();`      | `arr.rend();`      | Reverse iterator past the first element | O(1)            |
| `operator[]` | Accesses an element (no bounds checking)              | `arr[i];`          | `arr[2];`          | `3`                                     | O(1)            |
| `front()`    | Returns a reference to the first element              | `arr.front();`     | `arr.front();`     | `1`                                     | O(1)            |
| `back()`     | Returns a reference to the last element               | `arr.back();`      | `arr.back();`      | `5`                                     | O(1)            |

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                                     | Example Usage                                                                  | Output                     |
| ------------------------ | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------- |
| **Index-based loop**     | Using index-based loops to access elements directly by their index.             | `for (int i = 0; i < arr.size(); ++i) { cout << arr[i] << " "; }`              | `1 2 3 4 5`                |
| **Range-based for loop** | A simple loop to iterate over the array elements.                               | `for (auto &val : arr) { cout << val << " "; }`                                | `1 2 3 4 5`                |
| **Iterators**            | Using iterators to manually navigate through the array.                         | `auto it = arr.begin(); cout << *it;`                                          | `1`                        |
| **Reverse Iterators**    | Using reverse iterators to iterate backward.                                    | `for (auto it = arr.rbegin(); it != arr.rend(); ++it) { cout << *it << " "; }` | `5 4 3 2 1`                |
| **auto & const auto**    | Use of `auto` for type inference in the loop and `const auto` for immutability. | `for (auto &val : arr) { val *= 2; }`                                          | No output (modifies array) |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

You are given a fixed-size array with 5 elements. Perform the following operations:

1. Set all elements to a fixed value using `fill()`.
2. Access and print the first and last elements.
3. Swap the array with another array of the same size.
4. Print the array after swapping.

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    // Create an array of size 5
    array<int, 5> arr = {1, 2, 3, 4, 5};
    array<int, 5> arr2 = {10, 20, 30, 40, 50};

    // 1. Set all elements to 100
    arr.fill(100);

    // 2. Print the first and last elements
    cout << "First Element: " << arr.front() << endl; // Output: 100
    cout << "Last Element: " << arr.back() << endl;  // Output: 100

    // 3. Swap arr with arr2
    arr.swap(arr2);

    // 4. Print the array after swapping
    cout << "Array after swapping: ";
    for (const auto& val : arr) {
        cout << val << " ";
    }

    return 0;
}
```

#### 💡 **Output**:

```
First Element: 100
Last Element: 100
Array after swapping: 10 20 30 40 50
```

#### ⏱️ **Time Complexity**:

* **Fill**: O(n).
* **Swap**: O(1).
* **Access**: O(1).
