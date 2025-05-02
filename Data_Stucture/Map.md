---
title: "Map"
date: "2025-05-02"
tags: ["Data Structure"]
categories: ["技術筆記"]
draft: true
---
# Map
Map 是一種 關聯式容器（Associative Container），用來儲存 Key-Value 對（鍵值對），每個 key 是唯一的。`

### 函式
| 操作      | 複雜度      | 說明        |
| ---------- | -------- | --------- |
| `m[key] = value`        | O(log n) | 插入或更新                 |
| `m.at(key)`             | O(log n) | 查找 key，若不存在會 throw    |
| `m.find(key)`           | O(log n) | 回傳 iterator           |
| `m.count(key)`          | O(log n) | 是否存在此 key（回傳 0 或 1）   |
| `m.erase(key)`          | O(log n) | 移除該 key-value 對       |
| `m.lower_bound(key)`    | O(log n) | 找第一個 ≥ key 的 iterator |
| `m.upper_bound(key)`    | O(log n) | 找第一個 > key 的 iterator |
| `m.begin()` / `m.end()` | O(1)     | 起始與結尾 iterator        |
| 遍歷整個 map                | O(n)     | key 會依序輸出（已排序）        |

### 小結
`C++ map` 是用 `紅黑樹` 實作的自動排序關聯式容器，主要特點是：
* Key 唯一
* 自動排序（升序）
* 插入/查找/刪除都是 O(log n)