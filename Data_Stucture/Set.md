---
title: "Set"
date: "2025-05-02"
tags: ["Data Structure"]
categories: ["技術筆記"]
draft: true
---
# Set
`「用來儲存不重複、且自動排序的元素。」`

並且是用 「紅黑樹（Red-Black Tree）」 實作的。
這是一種「自平衡的二元搜尋樹（BST）」，能夠讓操作在最壞情況下都維持 O(log n)。


### 函式
| 操作    | 時間複雜度  | 說明      |
| ------- | ---------- | -------- |
| `s.insert(x)`  | O(log n) | 插入元素，若已存在則不插入        |
| `s.erase(x)`            | O(log n)   | 刪除元素                 |
| `s.find(x)`             | O(log n)   | 查找元素是否存在，回傳 iterator |
| `s.count(x)`            | O(log n)   | 判斷元素是否存在（回傳 0 或 1）   |
| `s.lower_bound(x)`      | O(log n)   | 找到第一個 ≥ x 的 iterator |
| `s.upper_bound(x)`      | O(log n)   | 找到第一個 > x 的 iterator |
| `s.begin()` / `s.end()` | O(1)       | 拿到 iterator 起點／尾端    |
| 遍歷整個 set（for-each）      | O(n)       | 按照排序順序從小到大           |
| 建立 set（插入 n 個元素）        | O(n log n) | 每次插入都 log n 次        |
