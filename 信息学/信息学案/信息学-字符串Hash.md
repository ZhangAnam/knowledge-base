# 考点2：字符串Hash

> 信息学 | 字符串 | NOI大纲

---

## 📌 核心概念

### 字符串Hash
将字符串映射为整数，利用整数比较代替字符串比较

### 常用Hash函数
```cpp
// 自然溢出法
unsigned long long hash = 0;
for (char c : s) hash = hash * P + c;

// 模版法
int hash = 0;
for (char c : s) hash = (hash * P + c) % MOD;
```

---

## 📌 前缀Hash

### 预处理
```cpp
const ull P = 1315423911ULL;
vector<ull> h(n+1), p(n+1);

h[0] = 0;
p[0] = 1;
for (int i = 1; i <= n; i++) {
    h[i] = h[i-1] * P + s[i-1];
    p[i] = p[i-1] * P;
}
```

### 获取子串Hash
```cpp
ull getHash(int l, int r) { // [l,r)
    return h[r] - h[l] * p[r-l];
}
```

---

## 📌 应用场景

1. 字符串去重
2. 字符串相同判断
3. 最长回文子串
4. 字符串子串出现次数

---

## 📝 典型例题

### 例1：判断回文串
判断字符串s是否为回文串。

> 📋 答案
> 正向Hash和逆向Hash对比
