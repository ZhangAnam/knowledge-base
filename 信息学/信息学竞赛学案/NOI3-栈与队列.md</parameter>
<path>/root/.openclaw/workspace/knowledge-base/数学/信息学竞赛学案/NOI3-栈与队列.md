# NOI学案 3：栈与队列

> 信息学竞赛 | 基础数据结构

---

## 📌 核心知识点

### 栈 Stack
- LIFO后进先出
- 应用：括号匹配、表达式求值、DFS

### 队列 Queue
- FIFO先进先出
- 应用：BFS、循环队列、双端队列

### 单调栈/队列
- 单调递增/递减
- 应用：求下一个更大/更小元素

---

## 📝 典型例题

### 表达式求值（中缀→后缀）
```cpp
// 运算符优先级
int priority(char op) {
    if (op == '+' || op == '-') return 1;
    if (op == '*' || op == '/') return 2;
    if (op == '^') return 3;
    return 0;
}
```

### 单调栈-下一个更大元素
```cpp
vector<int> nextGreater(vector<int>& a) {
    stack<int> st;
    vector<int> ans(a.size(), -1);
    for (int i = 0; i < a.size(); i++) {
        while (!st.empty() && a[st.top()] < a[i]) {
            ans[st.top()] = i;
            st.pop();
        }
        st.push(i);
    }
    return ans;
}
```

---

## 🧪 配套练习

1. 用栈实现队列
2. 每日温度（单调栈）
3. 火车进站（栈+队列）

---

## 📋 参考答案

1. 用两个栈
2. P1948 逆波兰表达式求值
3. P1041 传染病控制

---

> 📝 课后作业：洛谷相应题目
