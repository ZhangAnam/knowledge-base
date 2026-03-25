# 考点11：STL容器

> 信息学 | 工具 | NOI大纲

---

## 📌 常用容器

### set（集合）
```cpp
set<int> s;
s.insert(x);      // 插入
s.erase(x);       // 删除
s.find(x);        // 查找，返回迭代器
s.size();         // 大小
s.empty();        // 是否为空
```

### multiset（可重集合）
```cpp
multiset<int> ms;
ms.insert(x);
ms.erase(ms.find(x)); // 删除一个
```

### unordered_map（哈希表）
```cpp
unordered_map<string, int> mp;
mp["key"] = value;
if (mp.count(key)) // 查找
```

### map（红黑树）
```cpp
map<string, int> mp;
mp["a"] = 1;
for (auto [k, v] : mp) // 遍历
```

---

## 📌 容器选择

| 场景 | 推荐容器 |
|------|---------|
| 去重、有序 | set |
| 可重复、有序 | multiset |
| 快速查找 | unordered_map |
| 有序键值对 | map |
| 队列/栈 | queue/stack |
| 堆 | priority_queue |

---

## 📝 典型例题

### 例1：去重排序
将数组去重并排序。

> 📋 答案
```cpp
set<int> s(a.begin(), a.end());
```

---

## 📋 课后作业

1. 掌握各容器用法
2. 根据场景选择合适容器
3. 理解时间复杂度
