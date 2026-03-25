# NOI学案 9：KMP与字符串

> 信息学竞赛 | 字符串

---

## 📌 核心知识点

### KMP
- 前缀函数 π[i]：最长相等前后缀
- 失配时跳转next数组

### 字符串哈希
- Rabin-Karp
- 滚动哈希

### AC自动机
- KMP+Trie
- .fail指针

---

## 📝 典型例题

### KMP模板
```cpp
vector<int> getPi(string s) {
    int n = s.size();
    vector<int> pi(n);
    for (int i = 1; i < n; i++) {
        int j = pi[i-1];
        while (j > 0 && s[i] != s[j]) j = pi[j-1];
        if (s[i] == s[j]) j++;
        pi[i] = j;
    }
    return pi;
}

// 匹配
vector<int> kmp(string text, string pattern) {
    vector<int> pi = getPi(pattern);
    vector<int> ans;
    int j = 0;
    for (int i = 0; i < text.size(); i++) {
        while (j > 0 && text[i] != pattern[j]) j = pi[j-1];
        if (text[i] == pattern[j]) j++;
        if (j == pattern.size()) {
            ans.push_back(i - j + 1);
            j = pi[j-1];
        }
    }
    return ans;
}
```

---

## 🧪 配套练习

1. P3375 KMP模板
2. P5410 哈希
3. P3808 AC自动机

---

## 📋 答案

1. 模板
2. 滚动哈希
3. fail指针

---

> 📝 课后作业：洛谷相应题目
