# NOI学案 7：线性DP与区间DP

> 信息学竞赛 | 动态规划

---

## 📌 核心知识点

### 线性DP
- 最长上升子序列 LIS
- 最长公共子序列 LCS
- 数字三角形

### 区间DP
- 合并石子
- 矩阵链乘
- 括号序列

---

## 📝 典型例题

### LIS O(n log n)
```cpp
vector<int> LIS(vector<int>& a) {
    vector<int> tail;
    for (int x : a) {
        auto it = lower_bound(tail.begin(), tail.end(), x);
        if (it == tail.end()) tail.push_back(x);
        else *it = x;
    }
    return tail;
}
```

### 区间DP模板
```cpp
for (int len = 2; len <= n; len++) {
    for (int l = 1; l + len - 1 <= n; l++) {
        int r = l + len - 1;
        for (int k = l; k < r; k++) {
            f[l][r] = max(f[l][r], f[l][k] + f[k+1][r] + cost);
        }
    }
}
```

---

## 🧪 配套练习

1. P1020 导弹拦截（LIS）
2. P1092 括号配对（区间DP）
3. P3146 石子合并

---

## 📋 答案

1. DP或二分
2. f[l][r] = max(f[l][r-1], f[l+1][r])
3. 环形处理

---

> 📝 课后作业：洛谷相应题目
