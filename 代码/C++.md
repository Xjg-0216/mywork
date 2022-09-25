### C++

#### 输入输出

**只有一个或几个输入**

```C++
int main(){
    int a, b, c;
    cin >> a >> b >> c;
    cout << a + b + c << endl;
}
```

**先给数组元素个数，再给一行元素**

n, m分别是接下来要给的两个数组元素的个数， 输入样例：

```C++
5 2
1 4 2 6 5
2 3
```



```C++
int main(){
    int n, m;
    cin >> n >> m;
    vector<int> nums1(n);
    for (int i = 0; i < n; ++i) cin >> nums1[i];
    vector<int> nums2(m);
    for (int i = 0; i < m; ++i) cin >> nums[i];
    }
}
```

**行数未知**

```c++
#include<iostream>
using namespace std;
int main(){
    int n, m;
    vector<int> res;
    while (cin >> n >> m){
        res.push_back(n +m);
        cout << n + m << endl;
    }
}
```

**使用cin.get()， 判断换行符**





```c++
class SolutionP{
public:
    {
        int search()
    }
}
```

