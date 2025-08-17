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
}
