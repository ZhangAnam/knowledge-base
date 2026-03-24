# NOI学案 10：树与二叉树

> 信息学竞赛 | 数据结构

---

## 📌 核心知识点

### 树的遍历
- 前序/中序/后序
- 层次遍历（BFS）

### 二叉树
- 链式存储
- 数组存储（完全二叉树）

### 树的直径/重心
- 两次DFS/BFS
- 树DP

---

## 📝 典型例题

### 树的直径
```cpp
int dfs(int u, int fa) {
    int max1 = 0, max2 = 0;
    for (int v : g[u]) if (v != fa) {
        int d = dfs(v, u) + 1;
        if (d > max1) { max2 = max1; max1 = d; }
        else if (d > max2) max2 = d;
    }
    ans = max(ans, max1 + max2);
    return max1;
}
```

### LCA最近公共祖先
- 倍增
- 树剖

---

## 🧪 配套练习

1. P3376 树上最近公共祖先
2. P1352 欢迎宴会
3. P1087 营业额统计

---

## 📋 答案

1. 两次DFS或倍增
2. 二叉树遍历
3. 中序遍历

---

> 📝 课后作业：洛谷相应题目
