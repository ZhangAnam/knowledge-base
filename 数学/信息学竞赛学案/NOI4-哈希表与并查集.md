# NOI学案 4：哈希表与并查集

> 信息学竞赛 | 数据结构

---

## 📌 核心知识点

### 哈希表 Hash Table
- 散列函数
- 冲突处理：链地址法、开放地址法
- 字符串哈希

### 并查集 Union-Find
- 路径压缩
- 按秩合并
- 应用：连通性判断、集合合并

---

## 📝 典型例题

### 并查集模板
```cpp
class UnionFind {
    vector<int> parent, rank;
public:
    UnionFind(int n) {
        parent.resize(n);
        rank.assign(n, 0);
        iota(parent.begin(), parent.end(), 0);
    }
    
    int find(int x) {
        if (parent[x] != x) 
            parent[x] = find(parent[x]);
        return parent[x];
    }
    
    void unite(int x, int y) {
        x = find(x); y = find(y);
        if (x == y) return;
        if (rank[x] < rank[y]) swap(x, y);
        parent[y] = x;
        if (rank[x] == rank[y]) rank[x]++;
    }
};
```

### 食物链（NOI2002）
- 三种关系：同类、捕食、被捕食
- 用带权并查集维护

---

## 🧪 配套练习

1. P3367 并查集模板
2. P1551 亲戚
3. P1892 食物链

---

## 📋 参考答案

1. 模板题
2. 连通性判断
3. 带权并查集：relation[x]表示与根的关系

---

> 📝 课后作业：洛谷相应题目
