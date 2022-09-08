### ACM模式下输入输出

对于传统ACM的OJ模式题目， 程序需要`stdin`（标准输入）读取输入，然后`stdout`（标准输出）来打印结果。







注意事项：

1、在线编程， 需要导入`sys`, 利用`sys.stdin.strip().readline().split()`读取数据， 一行这样的代码， 仅仅代表读取一行， 如果需要读取多行，可以用多行这样的代码， 或者用`while True`循环读取。

2、牛客结果以`print`打印的结果为准

3、充分考虑代码的复杂度， 能简洁就简洁



#### 方式1：

1、从控制台输入若干数字， 并以空格分隔

2、输出结果为以空格分隔的字符串

```python
def in_put():
    num = raw_input()
    num2 = num.split(' ')
    for i in range(len(nums2)):
        num2[i] = int(num2[i])
    return num2

def out_put():
    s = " ".join(str(i) for i in x)
    return s
```

#### 方式2：

牛客网推荐使用`sys.stdin.readline()`形式输入， 输出用`print()`

`readline()`从文件读取整行，包括'\n'字符，

`strip()`只能用于移除字符串开头和结尾指定的字符（默认为空格或换行符）或字符序列

`split()`默认分割所有的空字符， 包括空格、换行(\n)、制表符(\t)等，返回分割后的字符串列表。

**读一行输入：(对于输入只有一行的可以这样读)**

```python
import sys 
s = sys.stdin.readline().strip()
print(s)
```

**如果这一行中有多个值可以通过split分割**成列表

```python
import sys
s = sys.stdin.readline().strip().split(' ')
print(s) 
```

**读多行：**

```python
import sys
data = []
while True:
    s = sys.stdin.readline().strip()
    if not s:
        break
    data.append(s)
print(data)
```

**读单个数字**

```
n = int(input())
```

或者

```python
import sys
n = int(sys.stdin.readline().strip())
```

**读两个数字**

```python
import sys
m, n = map(int, sys.stdin.readline().strip().split())
```

**读多个数字**

```python
import sys
data = list(map(int, sys.stdin.readline().strip().split()))
```





### 输出

**对于['1', '2', '3', '4']这样的格式要求变成1 2 3 4**

```python
a = ['1', '2', '3', '4']
print(''.join(a)) # 引号中没有空格， 输出为1234
print(' '.join(a)) # 引号中有空格， 输出为1 2 3 4
```

