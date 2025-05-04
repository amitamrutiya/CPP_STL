## 🚀 **STL: `string`**

#### 🧠 **What the container is used for**:

* **`string`** is a container that holds a sequence of characters (text). It is a sequence of characters that can be dynamically resized.
* It is primarily used for working with textual data, such as reading input, manipulating strings, or performing string-based operations.

#### 📍 **Where it is preferred and why**:

* **Preferred** when:

  * You need to manipulate text data.
  * You require dynamic size changes (unlike `char[]`).
  * You need to perform common operations like concatenation, searching, substring extraction, etc.

#### 🌍 **Real-world or DSA use cases**:

* **Real-world:** Storing and manipulating names, addresses, or any other form of textual data in applications.
* **DSA:** Common in problems related to string matching, palindrome checking, substring extraction, pattern matching, etc.

#### 🔧 **Internal data structure and behavior**:

* Internally, `string` is implemented as a dynamic array of characters.
* It automatically manages memory as needed, growing or shrinking as characters are added or removed.

#### ⚖️ **Advantages and limitations**:

* **Advantages**:

  * Provides dynamic sizing, so you don’t have to worry about buffer overflows.
  * Offers a variety of built-in methods for string manipulation.
  * Compatible with standard C++ features like iterators.
* **Limitations**:

  * The overhead of dynamic memory allocation, especially for small strings.
  * May not be as efficient as using fixed-size arrays in memory-constrained environments.

#### 🚫 **When not to use it**:

* When working in extremely memory-constrained environments, or when you are sure the string will have a fixed size.
* When working with fixed-length strings (consider `char[]` for such cases).

---

### 🧠 **Time & Space Complexities for `string`**

| Operation         | Time Complexity | Space Complexity |
| ----------------- | --------------- | ---------------- |
| Construction      | O(1)            | O(n)             |
| Access (by index) | O(1)            | O(1)             |
| Size              | O(1)            | O(1)             |
| Concatenation     | O(n)            | O(n)             |
| Searching         | O(n)            | O(1)             |

---

### 📚 **15 Important Methods for `string`**

| Method      | Description                                      | Syntax                              | Example Usage                               | Output          | Time Complexity |
| ----------- | ------------------------------------------------ | ----------------------------------- | ------------------------------------------- | --------------- | --------------- |
| `size()`    | Returns the length of the string.                | `str.size()` or `str.length()`      | `string str = "hello"; cout << str.size();` | `5`             | O(1)            |
| `empty()`   | Checks if the string is empty.                   | `str.empty()`                       | `cout << str.empty();`                      | `0` (false)     | O(1)            |
| `append()`  | Appends a string to the current string.          | `str.append("additional")`          | `str.append(" world");`                     | `"hello world"` | O(n)            |
| `substr()`  | Extracts a substring from the string.            | `str.substr(start, length)`         | `str.substr(0, 3)`                          | `"hel"`         | O(n)            |
| `find()`    | Finds the first occurrence of a substring.       | `str.find("substring")`             | `str.find("l");`                            | `2`             | O(n)            |
| `replace()` | Replaces part of the string with another string. | `str.replace(start, length, "new")` | `str.replace(0, 5, "hi")`                   | `"hi world"`    | O(n)            |
| `erase()`   | Erases characters from the string.               | `str.erase(start, length)`          | `str.erase(0, 3);`                          | `"lo"`          | O(n)            |
| `insert()`  | Inserts a string at a specific position.         | `str.insert(index, "new")`          | `str.insert(5, " world")`                   | `"hello world"` | O(n)            |
| `c_str()`   | Returns a C-style character array.               | `str.c_str()`                       | `const char* c = str.c_str();`              | `"hello"`       | O(1)            |
| `compare()` | Compares two strings lexicographically.          | `str.compare("other")`              | `str.compare("hello")`                      | `0`             | O(n)            |

---

### 🧰 **Methods of Initialization**

#### 🛠️ **Declaration Variants**

* **Basic String Declaration**:

  ```cpp
  string str = "hello";
  ```

* **Using Constructor with Specific Size**:

  ```cpp
  string str(5, 'a'); // "aaaaa"
  ```

* **From Another String**:

  ```cpp
  string str2 = str; // Copy constructor
  ```

* **With Custom Data Types**:

  ```cpp
  struct Person {
      string name;
      int age;
  };
  string name = "John";
  ```

* **Using `getline()` for Input**:

  ```cpp
  string str;
  getline(cin, str); // Reads a full line of text
  ```

---

### 🔄 **Traversal Techniques**

| Technique                | Description                                                       | Example Usage                                                    | Output  |
| ------------------------ | ----------------------------------------------------------------- | ---------------------------------------------------------------- | ------- |
| **Index-based loop**     | Using a standard for loop to access individual characters.        | `for(int i = 0; i < str.size(); i++) cout << str[i];`            | `hello` |
| **Range-based for loop** | Using `for` loop to iterate through each character in the string. | `for(char c : str) cout << c;`                                   | `hello` |
| **Iterators**            | Using iterators to traverse the string.                           | `for(auto it = str.begin(); it != str.end(); ++it) cout << *it;` | `hello` |

---

### 🧪 **Advanced Practice Problem**

#### 🏅 **Problem**:

Given a string, determine if it is a palindrome (the string reads the same backward as forward).

#### 📝 **Step-by-Step Solution**:

```cpp
#include <iostream>
#include <string>
using namespace std;

bool isPalindrome(const string& str) {
    int left = 0, right = str.size() - 1;
    while (left < right) {
        if (str[left] != str[right]) return false;
        left++;
        right--;
    }
    return true;
}

int main() {
    string str = "madam";
    if (isPalindrome(str)) {
        cout << "Palindrome" << endl;
    } else {
        cout << "Not Palindrome" << endl;
    }
    return 0;
}
```

#### 💡 **Output**:

```
Palindrome
```

#### ⏱️ **Time Complexity**:

* Checking if palindrome: O(n), where `n` is the length of the string.

#### 🏋️‍♂️ **Space Complexity**:

* O(1), as we are using a constant amount of extra space.
