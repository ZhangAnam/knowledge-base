# 考点1：字符串匹配 - KMP算法

> 信息学 | 字符串 | NOI大纲

---

## 📌 核心概念

### KMP解决的问题
高效地在文本串中查找模式串的出现位置，避免重复比较

### Next数组
next[i] = 最长相等前后缀长度

### 核心思想
当匹配失败时，利用已经匹配的信息，避免回溯

---

## 📌 算法实现

### 求Next数组
```cpp
void getNext(string p) {
    next[0] = -1;
    int j = 0, k = -1;
    while (j < p.length()-1) {
        if (k==-1 || p[j]==p[k]) {
            next[++j] = ++k;
        } else {
            k = next[k];
        }
    }
}
```

### KMP匹配
```cpp
int kmp(string s, string p) {
    getNext(p);
    int i = 0, j = 0;
    while (i < s.length() && j < p.length()) {
        if (j==-1 || s[i]==p[j]) {
            i++; j++;
        } else {
            j = next[j];
        }
        if (j == p.length()) {
            return i - j; // 匹配成功
        }
    }
    return -1;
}
```

---

## 📌 时间复杂度
- 构建next数组：O(m)
- 匹配：O(n)
- 总计：O(n+m)

---

## 📝 典型例题

### 例1：实现strStr
在haystack中找needle首次出现的位置。

> 📋 答案
> 使用KMP算法，见上方代码

---

## 📋 课后作业

1. 理解next数组的含义
2. 能手写KMP算法
3. 理解为什么KMP比朴素匹配快
