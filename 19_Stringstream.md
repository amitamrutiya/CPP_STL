# stringstream in C++

## Overview

`stringstream` is a class in C++ (from `<sstream>`) that allows you to perform input and output operations on strings, similar to how you use `cin` and `cout` for console I/O. It is widely used for parsing, formatting, and type conversion between strings and other data types.

---

## Properties and Operations

| Property / Operation     | Use Case                                  | Time Complexity | Example |
|-------------------------|--------------------------------------------|-----------------|---------|
| **Construction**        | Create a stringstream object               | O(1)            | `stringstream ss;`<br>`stringstream ss("12 34");` |
| **Insertion (`<<`)**    | Add data (string, int, etc.) to stream     | O(n)            | `ss << "abc " << 42;` |
| **Extraction (`>>`)**   | Extract data (tokenize, parse types)       | O(n)            | `int x; ss >> x;` |
| **str()**               | Get the current string contents            | O(1)            | `string s = ss.str();` |
| **str(string)**         | Set the stream’s buffer to a new string    | O(n)            | `ss.str("new content");` |
| **clear()**             | Reset stream state flags                   | O(1)            | `ss.clear();` |
| **Parsing**             | Tokenize space-separated values            | O(n)            | See parsing example below |
| **Type Conversion**     | Convert between string and numbers         | O(n)            | See conversion example below |

---

## Example Use Cases

### 1. Basic Construction and Insertion

```cpp
stringstream ss;
ss << "Name: " << "John" << ", Age: " << 25;
string info = ss.str(); // "Name: John, Age: 25"
```

---

### 2. Parsing Space-Separated Values

```cpp
string input = "10 20 30";
stringstream ss(input);
int num;
while (ss >> num) {
    // num is 10, then 20, then 30
}
```

---

### 3. Type Conversion

#### int to string

```cpp
int x = 123;
stringstream ss;
ss << x;
string str = ss.str(); // "123"
```

#### string to int

```cpp
string str = "456";
stringstream ss(str);
int x;
ss >> x; // x = 456
```

---

### 4. Clearing and Reusing

```cpp
ss.str("");    // Remove contents
ss.clear();    // Reset error flags
```

---

## Advanced Examples

### 1. Splitting a String by Delimiter

```cpp
string line = "apple,banana,orange";
stringstream ss(line);
string item;
while (getline(ss, item, ',')) {
    // item will be "apple", then "banana", then "orange"
}
```

---

### 2. Reading Mixed Types from a String

```cpp
string line = "42 3.14 hello";
stringstream ss(line);

int i;
double d;
string s;

ss >> i >> d >> s;
// i = 42, d = 3.14, s = "hello"
```

---

### 3. Formatting Output with Precision

```cpp
double pi = 3.14159265;
stringstream ss;
ss.precision(3);
ss << fixed << pi;
string s = ss.str(); // "3.142"
```

---

### 4. Custom Parsing: Extract Key-Value Pairs

```cpp
string input = "a=1 b=2 c=3";
stringstream ss(input);
string pair;
while (ss >> pair) {
    size_t pos = pair.find('=');
    string key = pair.substr(0, pos);
    string value = pair.substr(pos + 1);
    // key: "a", value: "1" etc.
}
```

---

### 5. Reverse Conversion: String to Double to Int

```cpp
string str = "123.45";
stringstream ss(str);
double d;
ss >> d; // d = 123.45

stringstream ss2;
ss2 << static_cast<int>(d);
string intStr = ss2.str(); // "123"
```

---

## Typical Use Cases

- **Parsing numbers and words from a string** (e.g., user input, data files)
- **Splitting strings by space or delimiter**
- **Converting between string and numeric types**
- **Building formatted strings from multiple variables**
- **Custom parsing logic for configuration or log files**

---

## Time Complexity

- **Insertion/Extraction (`<<`, `>>`)**: O(n), n = number of characters processed.
- **Construction/str()**: O(1) for getting; O(n) for setting contents.
- **Parsing**: O(n) for full string parse.

---

## Notes

- Always call `clear()` after an extraction failure before reusing the stream.
- Not thread-safe.
- Memory usage grows with string content.

---

## References

- [cplusplus.com — stringstream](http://www.cplusplus.com/reference/sstream/stringstream/)
- [cppreference.com — stringstream](https://en.cppreference.com/w/cpp/io/basic_stringstream)
