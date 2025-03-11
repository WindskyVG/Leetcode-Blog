# 📌 Problem Breakdown - kama 58.区间和

## 🔍 Problem Statement
- **Category:**  [[Array]] [[Prefix Sum]]
- **Problem:** 
- **Difficulty:**  Easy 

## 🧠 Initial Thoughts
- **Understanding the problem**:  
- **First approach that came to mind**:  

## 🛠 Solution Approach
- **Idea:**  when input, record the sum of the numbers from beginning to the current index, this way we can easily find the prefix sum easily!

前缀和的思想是重复利用计算过的子数组之和，从而降低区间查询需要累加计算的次数。

前缀和 在涉及计算区间和的问题时非常有用！

前缀和的思路其实很简单，我给大家举个例子很容易就懂了。

例如，我们要统计 vec[i] 这个数组上的区间和。

我们先做累加，即 p[i] 表示 下标 0 到 i 的 vec[i] 累加 之和。
 
- **Time Complexity:**  
- **Space Complexity:**  

### **Code Implementation**
```c++
#include <iostream>
#include <vector>
using namespace std;
int main() {
    int n, a, b;
    cin >> n;
    vector<int> vec(n);
    int input;
    int sum = 0;
    for (int i = 0; i < n; i++){
        cin >> input;
        sum+=input;
        vec[i] = sum;
    } 
    while (cin >> a >> b) {
        //int sum = 0;
        // 累加区间 a 到 b 的和
        //for (int i = a; i <= b; i++) sum += vec[i];
        cout << vec[b] - vec[a-1] << endl;
    }
} 
```

