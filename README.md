# 🧠 STL for DSA – Organized for Easy Memorization

---

### 🗂️ 1. **Containers** – “*Store data efficiently*”

#### 📦 A. **Sequence Containers** – Maintain *order of insertion*

| Container      | Description                           |
| -------------- | ------------------------------------- |
| `vector`       | Dynamic array (resizable)             |
| `deque`        | Double-ended queue (insert both ends) |
| `list`         | Doubly linked list                    |
| `forward_list` | Singly linked list (C++11)            |
| `array`        | Fixed-size array (C++11)              |

#### 📚 B. **Associative Containers** – *Sorted* data, based on BST

| Container  | Description                         |
| ---------- | ----------------------------------- |
| `set`      | Unique, sorted elements             |
| `multiset` | Sorted elements, duplicates allowed |
| `map`      | Key-value pairs, keys unique        |
| `multimap` | Key-value pairs, keys can repeat    |

#### 🧮 C. **Unordered Containers** – *Hashed*, faster on average

| Container            | Description                   |
| -------------------- | ----------------------------- |
| `unordered_set`      | Unique, not sorted            |
| `unordered_multiset` | Duplicates, not sorted        |
| `unordered_map`      | Key-value pairs, fast lookup  |
| `unordered_multimap` | Duplicates in key-value pairs |

#### 🧱 D. **Container Adapters** – Built on other containers

| Adapter          | Description           | Backed by |
| ---------------- | --------------------- | --------- |
| `stack`          | LIFO                  | `deque`   |
| `queue`          | FIFO                  | `deque`   |
| `priority_queue` | Heap (max by default) | `vector`  |

---

### 🧭 2. **Iterators** – “*Navigate through containers*”

| Concept              | Description                   |
| -------------------- | ----------------------------- |
| `begin()`, `end()`   | Start & end of container      |
| `rbegin()`, `rend()` | Reverse traversal             |
| `auto`               | Type deduction for iterators  |
| `advance()`          | Move iterator forward         |
| `next()`, `prev()`   | Get next or previous iterator |
| `distance()`         | Count steps between iterators |

---

### 🧮 3. **Algorithms** – “*Built-in problem solvers*” (`<algorithm>`)

#### 🔽 A. **Sorting**

* `sort()`, `stable_sort()`
* `partial_sort()`, `nth_element()`

#### 🔍 B. **Searching**

* `binary_search()`
* `lower_bound()`, `upper_bound()`

#### 🔁 C. **Permutation**

* `next_permutation()`, `prev_permutation()`

#### 🔢 D. **Min/Max**

* `min()`, `max()`, `min_element()`, `max_element()`

#### 🔍 E. **Count/Find**

* `count()`, `find()`, `count_if()`, `find_if()`

#### 🔄 F. **Modifying**

* `reverse()`, `rotate()`, `unique()`, `remove()`, `fill()`, `replace()`

#### ➕ G. **Others**

* `accumulate()` – sum of a range (`<numeric>`)
* `all_of()`, `any_of()`, `none_of()` – condition check (C++11)

---

### 🧰 4. **Utility Tools** – “*Handy helpers*”

#### 👫 A. **Pairs & Tuples**

| Tool                    | Description             |
| ----------------------- | ----------------------- |
| `pair`                  | Combine two values      |
| `make_pair()`           | Create pair             |
| `tuple`                 | Combine multiple values |
| `make_tuple()`, `tie()` | Create and unpack       |

#### 🔁 B. **Function Tools**

| Tool           | Description                  |
| -------------- | ---------------------------- |
| `swap()`       | Swap values                  |
| `move()`       | Move semantics (C++11)       |
| `lambda`       | Inline anonymous functions   |
| Custom `cmp()` | Used in sorting, heaps, etc. |

---

### 🔠 5. **Strings** – “*Text handling*”

| Function                | Purpose                     |
| ----------------------- | --------------------------- |
| `substr()`, `find()`    | Extract & locate substrings |
| `insert()`, `erase()`   | Modify string contents      |
| `replace()`             | Replace part of a string    |
| `stoi()`, `to_string()` | String↔Number conversions   |

---

### 🧮 6. **Bit Manipulation & Math Helpers**

#### ⚙️ A. `bitset<N>` – Fixed size binary vector

* Functions: `set()`, `reset()`, `count()`, `to_string()`

#### 🧠 B. Built-in Bit Functions (GCC)

| Function               | Description          |
| ---------------------- | -------------------- |
| `__builtin_popcount()` | Count 1s in binary   |
| `__builtin_clz()`      | Count leading zeros  |
| `__builtin_ctz()`      | Count trailing zeros |

#### 📊 C. Math

* `pow()`, `abs()`, `sqrt()`, `log()`
* `gcd()` / `lcm()` (C++17)

---

### 🎓 Pro Tips

* Always use `emplace()` when performance matters (avoids copy)
* Use `auto` and range-based loops for clean code
* Know when to use `set` (sorted) vs `unordered_set` (faster)
* Learn STL by solving problems that *require* them (practice!)

---
