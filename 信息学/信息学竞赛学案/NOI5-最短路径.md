# NOI学案 5：最短路径算法

> 信息学竞赛 | 图论

---

## 📌 核心知识点

### Dijkstra算法
- 单源最短路
- 不能处理负权边
- 堆优化 O(m log n)

### Bellman-Ford
- 能检测负环
- SPFA：队列优化

### Floyd-Warshall
- 多源最短路 O(n³)
- 动态规划思想

---

## 📝 典型例题

### Dijkstra模板
```cpp
vector<int> dijkstra(int s) {
    vector<int> dist(n, INF);
    vector<bool> vis(n, false);
    priority_queue<pair<int,int>, vector<...>, greater<...>> pq;
    dist[s] = 0;
    pq.push({0, s});
    while (!pq.empty()) {
        auto [d, u] = pq.top(); pq.pop();
        if (vis[u]) continue;
        vis[u] = true;
        for (auto [v, w] : g[u]) {
            if (dist[v] > dist[u] + w) {
                dist[v] = dist[u] + w;
                pq.push({dist[v], v});
            }
        }
    }
    return dist;
}
```

### 次短路
- 记录最短和次短

---

## 🧪 配套练习

1. P4779 单源最短路径
2. P2850 最短路径计数
3. 求负环

---

## 📋 参考答案

1. Dijkstra堆优化
2. DP：f[v] = Σf[u]（最短路条数）
3. Bellman-Ford/SPFA检测

---

> 📝 课后作业：洛谷相应题目
