# 📌 Problem Breakdown - kama 44.开发商购买土地

## 🔍 Problem Statement
- **Category:**  
- **Problem:** 
- **Difficulty:**  Medium 

## 🧠 Initial Thoughts
- **Understanding the problem**:  
- **First approach that came to mind**:  

## 🛠 Solution Approach
- **Idea:**  在matrix中，用区间和把整个matrix合并到两个array里（横和竖），然后找最小。
	- 我们要找的最小区间是 |A-B|，A=horizontalCut，B=sum-horizontalCut，
	- 所以得的答案是 |horizontalCut - （sum-horizontalCut）|，
	- 跟sum - horizontalCut - horizontalCut一样
- **Time Complexity:**  
- **Space Complexity:**  

### **Code Implementation**
```c++
#include <iostream>
#include <vector>
#include <climits>

using namespace std;
int main () {
    int n, m;
    cin >> n >> m;
    int sum = 0;
    vector<vector<int>> vec(n, vector<int>(m, 0)) ;
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            cin >> vec[i][j];
            sum += vec[i][j];
        }
    }
    // 统计横向
    vector<int> horizontal(n, 0);
    for (int i = 0; i < n; i++) {
        for (int j = 0 ; j < m; j++) {
            horizontal[i] += vec[i][j];
        }
    }
    // 统计纵向
    vector<int> vertical(m , 0);
    for (int j = 0; j < m; j++) {
        for (int i = 0 ; i < n; i++) {
            vertical[j] += vec[i][j];
        }
    }
    int result = INT_MAX;
    int horizontalCut = 0;
    for (int i = 0 ; i < n; i++) {
        horizontalCut += horizontal[i];
        result = min(result, abs(sum - horizontalCut - horizontalCut));
    }
    int verticalCut = 0;
    for (int j = 0; j < m; j++) {
        verticalCut += vertical[j];
        result = min(result, abs(sum - verticalCut - verticalCut));
    }
    cout << result << endl;
}

```

