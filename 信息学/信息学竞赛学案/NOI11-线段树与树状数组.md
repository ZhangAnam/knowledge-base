# NOI学案 11：线段树与树状数组

> 信息学竞赛 | 数据结构

---

## 📌 核心知识点

### 线段树
- 区间修改/查询
- 懒标记下推
- 权值线段树

### 树状数组
- 单点修改/区间查询
-  BIT
-  逆序对

---

## 📝 典型例题

### 线段树区间加/区间求和
```cpp
struct SegTree {
    int n;
    vector<long long> sum, lazy;
    void build(int node, int l, int r) {
        if (l == r) { sum[node] = a[l]; return; }
        int mid = (l+r)/2;
        build(node*2, l, mid);
        build(node*2+1, mid+1, r);
        sum[node] = sum[node*2] + sum[node*2+1];
    }
    void pushDown(node, l, r) {
        if (lazy[node]) {
            // 下推标记
        }
    }
    void update(node, l, r, ql, qr, val) { ... }
    long long query(node, l, r, ql, qr) { ... }
};
```

### 树状数组
```cpp
void add(int idx, int val) {
    for (; idx <= n; idx += idx & -idx) bit[idx] += val;
}
long long sum(int idx) {
    long long res = 0;
    for (; idx > 0; idx -= idx & -idx) res += bit[idx];
    return res;
}
```

---

## 🧪 配套练习

1. P3372 线段树模板
2. P3368 树状数组模板
3. P1502 最大子段和

---

## 📋 答案

1. 线段树模板
2. BIT模板
3. 区间DP/线段树

---

> 📝 课后作业：洛谷相应题目
