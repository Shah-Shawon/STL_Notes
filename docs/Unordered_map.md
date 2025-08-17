# 🔹 What is `unordered_map`?

- `unordered_map` is an **associative container** in C++ STL.  
- It stores **key-value pairs** (like a dictionary or hashmap).  
- Internally, it uses a **hash table**.  
- Keys must be **unique** (duplicate keys are not allowed).  
- The elements are **not stored in any particular order** (unlike `map`, which keeps keys sorted).  

---

## 🔹 Data Structure
- Internally it uses a **Hash Table**.  
- A **hash function** is applied to the key to decide which bucket it belongs to.  
- Because of this, **insertion, deletion, and search are O(1) on average**.  

---

## 🔹 Syntax Example
```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<int, string> mp;

    // Insert
    mp[1] = "Alice";
    mp[2] = "Bob";
    mp.insert({3, "Charlie"});

    // Access
    cout << mp[1] << endl; // Alice

    // Search
    if (mp.find(2) != mp.end())
        cout << "Found: " << mp[2] << endl;

    // Iterate
    for (auto &p : mp) {
        cout << p.first << " => " << p.second << endl;
    }

    return 0;

# Unordered Map (C++ STL)

---

# `unordered_map` in C++

`unordered_map` is a hash table–based key-value container in C++.  
It provides very fast search/insert/delete operations with **O(1) average complexity**.  
Keys are **not ordered** (unlike `map`, which keeps keys sorted).

---

## 🔹 Common Functions

| Function         | Description                                 |
| ---------------- | ------------------------------------------- |
| `insert({k,v})`  | Insert a new key-value pair                 |
| `mp[key]`        | Access or assign value by key               |
| `find(key)`      | Search for key (returns iterator)           |
| `erase(key)`     | Remove element with given key               |
| `size()`         | Number of elements                          |
| `empty()`        | Checks if container is empty                |
| `clear()`        | Removes all elements                        |
| `count(key)`     | Returns 0 or 1 depending if key exists      |
| `bucket_count()` | Number of hash buckets                      |
| `load_factor()`  | Elements per bucket (measure of efficiency) |

---

## 🔹 Time Complexity

| Operation | Average Case | Worst Case |
| --------- | ------------ | ---------- |
| Insert    | O(1)         | O(n)       |
| Search    | O(1)         | O(n)       |
| Delete    | O(1)         | O(n)       |

⚠️ **Worst case** happens if too many keys collide into the same bucket (bad hash function).  
✅ But usually, performance is **O(1)**.  

---

## 🔹 When to Use?

Use `unordered_map` when:

- You need **fast lookup/insert/delete**.  
- Ordering of keys is **not important**.  

Examples:

- Counting frequency of elements (word/number counts).  
- Hash-based lookups (e.g., checking if an element exists).  
- Handling large datasets where `map` (`O(log n)`) might be slower.  

---

## 🔹 Difference Between `map` and `unordered_map`

| Feature        | `map` (Ordered)                 | `unordered_map` (Unordered) |
| -------------- | ------------------------------- | --------------------------- |
| Implementation | Balanced BST (Red-Black Tree)   | Hash Table                  |
| Order          | Keys sorted                     | No ordering                 |
| Time           | O(log n)                        | O(1) average                |
| Worst Case     | O(log n)                        | O(n)                        |
| Memory Usage   | Less                            | More (due to buckets)       |

---

## 🔹 Example: Frequency Count

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> arr = {1,2,3,1,2,1,4,3};
    unordered_map<int,int> freq;

    for(int x : arr){
        freq[x]++;
    }

    for(auto &p : freq){
        cout << p.first << " occurs " << p.second << " times\n";
    }
}
}

