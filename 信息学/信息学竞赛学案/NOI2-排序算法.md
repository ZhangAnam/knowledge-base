# NOI学案 2：排序算法

> 信息学竞赛 | 排序

---

## 📌 核心知识点

### 基础排序 O(n²)
- 冒泡排序：相邻交换
- 插入排序：扑克牌整理
- 选择排序：找最小交换

### 高级排序 O(n log n)
- 快速排序：分治+基准
- 归并排序：分治合并
- 堆排序：二叉堆

### 特殊排序
- 计数排序：桶思想 O(n+k)
- 基数排序：按位排序

---

## 📝 典型例题

### 归并排序求逆序对
```cpp
void mergeSort(int l, int r) {
    if (l == r) return;
    int mid = (l + r) / 2;
    mergeSort(l, mid);
    mergeSort(mid+1, r);
    merge(l, mid, r);
}

long long merge(int l, int m, int r) {
    // 合并时统计逆序对
    // 跨区间时：mid - i + 1
}
```

### 堆排序
```cpp
void heapify(int i, int n) {
    int largest = i;
    int l = 2*i, r = 2*i+1;
    if (l <= n && a[l] > a[largest]) largest = l;
    if (r <= n && a[r] > a[largest]) largest = r;
    if (largest != i) {
        swap(a[i], a[largest]);
        heapify(largest, n);
    }
}
```

---

## 🧪 配套练习

1. 手写快排/归并/堆排
2. 哪个排序算法最稳定？为什么？
3. 10⁵和10⁷数据选什么排序？

---

## 📋 参考答案

1. 略
2. 归并排序稳定
3. 10⁵：快排/归并；10⁷：需要O(n)额外空间的排序

---

> 📝 课后作业：洛谷P1048 采药（P1048）
