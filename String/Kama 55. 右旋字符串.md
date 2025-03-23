# 📌 Problem Breakdown - Kama 55. 右旋字符串

## 🔍 Problem Statement
- **Category:**  
- **Problem:** https://kamacoder.com/problempage.php?pid=1065
- **Difficulty:**  Easy 

## 🧠 Initial Thoughts
- **Understanding the problem**:  
- **First approach that came to mind**:  

## 🛠 Solution Approach
- **Idea:**  
	- 1. Reverse entire string, reverse front to n, reverse n to end
	- 2. Reverse begin to len-n. reverse from len-n to end, reverse entire string
- **Time Complexity:**  
- **Space Complexity:**  

### **Code Implementation**
```c++
// 版本一
#include<iostream>
#include<algorithm>
using namespace std;
int main() {
    int n;
    string s;
    cin >> n;
    cin >> s;
    int len = s.size(); //获取长度

    reverse(s.begin(), s.end()); // 整体反转
    reverse(s.begin(), s.begin() + n); // 先反转前一段，长度n
    reverse(s.begin() + n, s.end()); // 再反转后一段

    cout << s << endl;

} 
```



```cpp
// 版本二 
#include<iostream>
#include<algorithm>
using namespace std;
int main() {
    int n;
    string s;
    cin >> n;
    cin >> s;
    int len = s.size(); //获取长度
    reverse(s.begin(), s.begin() + len - n); // 先反转前一段，长度len-n ，注意这里是和版本一的区别
    reverse(s.begin() + len - n, s.end()); // 再反转后一段
    reverse(s.begin(), s.end()); // 整体反转
    cout << s << endl;

}
```


Left shift:
```cpp
#include<iostream>
#include<algorithm>
using namespace std;
int main() {
    int n;
    string s;
    cin >> n;
    cin >> s;
    int len = s.size(); //获取长度
    reverse(s.begin(), s.begin() + n); //  反转第一段长度为n 
    reverse(s.begin() + n, s.end()); // 反转第二段长度为len-n 
    reverse(s.begin(), s.end());  // 整体反转
    cout << s << endl;
}
```