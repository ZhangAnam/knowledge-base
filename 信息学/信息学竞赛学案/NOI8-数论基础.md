# NOI学案 8：数论基础

> 信息学竞赛 | 数学

---

## 📌 核心知识点

### 质数
- 埃拉托斯特尼筛法 O(n log log n)
- 线性筛 O(n)

### GCD/LCM
- 欧几里得算法
- 扩展欧几里得求逆元

### 模运算
- 费马小定理
- 中国剩余定理 CRT

---

## 📝 典型例题

### 线性筛质数
```cpp
vector<int> primes;
vector<int> isPrime(n+1, true);
isPrime[0] = isPrime[1] = false;
for (int i = 2; i <= n; i++) {
    if (isPrime[i]) primes.push_back(i);
    for (int p : primes) {
        if (i * p > n) break;
        isPrime[i * p] = false;
        if (i % p == 0) break;
    }
}
```

### 扩展欧几里得
```cpp
int exgcd(int a, int b, int &x, int &y) {
    if (b == 0) { x = 1; y = 0; return a; }
    int x1, y1;
    int g = exgcd(b, a % b, x1, y1);
    x = y1;
    y = x1 - a / b * y1;
    return g;
}
```

---

## �配套练习

1. 快速幂模板
2. 求逆元（扩展欧几里得）
3. CRT模板

---

## 📋 答案

1. 快速幂：分治思想
2. inv = (b^(p-2))%p (p为质数)
3. 逐个合并

---

> 📝 课后作业：洛谷相应题目
