`numpy`是python的一个扩展程序库，支持大量的维度数组与矩阵计算，此外也针对数组运算提供大量的数学函数库

##### 1、Numpy Ndarray 对象

numpy 最重要的一个特点就是N维数组对象的ndarray， 它是一系列同类型数据的集合，以0下标为开始进行集合中元素的索引

ndarray对象用于存放同类型元素的多维数组

ndarray中每个元素在内存中都有相同存储大小的区域

ndarray其内部由以下内容组成：

* 一个指向数据的指针
* 数据类型或dtype， 描述在数组中的固定大小值的格子
* 一个表示数组形状(shape）的元组，表示各维度大小的元组
* 一个跨度元组（stride）, 其中的整数指的是为了前进到当前维度下一个元素需要“跨过”的字节数

创建一个ndarray:

```python
>>> np.array([1, 2, 3], dtype="uint8")
Out[3]: array([1, 2, 3], dtype=uint8)
```

##### 2、numpy 数据类型

支持 `bool_`  、`int_`(int32或int64)、`int8`(字节-128到127)、`int16` `int32` `int64`

`uint8`(无符号整型 0 to 255)   `uint16` (无符号整型 0 to 65535)   `uint32` `uint64` 

`float_` (就是float64)、`float16`（半精度浮点数） `float32`（单精度浮点数）`float64`（双精度浮点数）

 `complex_`（就是complex128）、 `complex64`（复数，表示双32位浮点数）、 `complex128`（复数，表示双64位浮点数）

##### 3、numpy数组属性

`ndarray.ndim` : 数组的维度数量

`ndarray.shape`: 数组的维度

`ndarray.dtype`: ndarray的数据类型

`ndarray.real`: ndarray元素的实部

`ndarray.imag`: ndarray元素的虚部

`ndarray.data`: 包含实际数组元素的缓冲区，一般通过索引进行获取元素，不使用

##### 4、创建数据

**1)  np.empty(shape, dtype)         #创建一个空数组** 

```python
>>> np.empty([2, 3], dtype="float64")
[[6.23042070e-307 2.13619585e-306 2.00479016e+074]
 [2.46158080e+070 1.30892434e+084 8.45593934e-307]]
```

**2) np.zeros(shape, dtype)       #创建一个全零数组**

```python
>>> np.zeros([2, 2], dtype="float64")
[[0. 0.]
 [0. 0.]]
```

**3) np.ones(shape，dtype)      #创建一个全1数组**

```python
>>> np.ones([2, 2], dtype="float64")
[[1. 1.]
 [1. 1.]]
```

##### 5、从数值范围创建数组

**1） np.arange(start, stop, step, dtype)**

```python
>>> np.arange(1, 10, 2, "float32")
[1. 3. 5. 7. 9.]
```

**2) np.linspace(start, stop, num=50, dtype=None )** 等差数列

```python
>>> np.linspace(start=1, stop=10, num=5, dtype="float32")
[ 1.    3.25  5.5   7.75 10.  ]
```

**3） np.logsapce(start, stop, num=50, base=10, dtype=None)** 等比数列, 默认底数为10

```python
>>> np.logspace(start=1, stop=2, num = 5, dtype="float16")
[ 10.    17.78  31.62  56.22 100.  ]
```

##### 6、切片和索引

```python
>>> a = np.arange(10)
[0 1 2 3 4 5 6 7 8 9]
>>> s = slice(2, 7, 2) #内置函数，从索引2到索引7，间隔为2
>>> a[s]
[2 4 6]
```

**也可以通过冒号分隔切片**   `start:stop:step`

```python
>>> a = np.arange(10)
>>> b = a[2:7:2]
[2 4 6]
```

**整数数组索引** 

```python
x = np.array([[1, 2], [3, 4], [5, 6]])
y = x[[0, 1, 2], [0, 1, 0]]  # 获取数据中(0, 0) (1, 1)(2, 0)位置的元素
```

**布尔索引**

以下是获取大于5的元素

```python
>>> a = np.array([[1, 2, 3], [4, 5, 6] , [7, 8, 9]])
>>> a[a>5]
[6 7 8 9]
```

**花式索引**

利用整数数组进行索引，根据索引数组的值作为目标数组的某个轴的下标来取值。

```python
a = np.arange(32).reshape((8, 4)
a[[4, 2, 1, 7]]  #获取第4行，第2行，第1行，第7行
```

传入多个索引数组

```python
a = np.arange(32).reshape((8, 4))
a[np.ix_[1, 5, 7, 2], [0, 3, 1, 2]]#相当于获取一个新的数组，前面是重排的行数，后面是重排的列数
```

##### 7、广播

当运算中的2个数组的形状不同时， numpy自动触发广播机制，如：

```python
a = np.array([[0, 0, 0], [10, 10, 10], [20, 20, 20]])
b = np.array([0, 1, 2])
a + b
[[ 0  1  2]
 [10 11 12]
 [20 21 22]]
```

##### 8、数组操作

`np.reshape(arr)`：改变形状

`np.transpose()`:对换数组的维度, 与ndarray.T类似

```python
>>> a = np.arange(8).reshape(4, 2)
[[0 1 2 3]
 [4 5 6 7]]
>>> print(np.transpose(a))
[[0 4]
 [1 5]
 [2 6]
 [3 7]]
>>> print(a.T)
[[0 4]
 [1 5]
 [2 6]
 [3 7]]
```

`np.swapaxes(arr, axis1, axis2)` # 交换数组的两个轴

```python
>>> a = np.arange(8).reshape(4, 2)
[[0 1 2 3]
 [4 5 6 7]]
>>> print(np.swapaxes(a, 0, 1))
[[0 4]
 [1 5]
 [2 6]
 [3 7]]
```

`np.expand_dims`

通过在指定位置插入新的轴来扩展数组形状

```python
a = x = np.array(([1, 2], [3, 4]))
y = np.expand_dims(a, 0)
print(a)
print(y)

[[1 2]
 [3 4]]
[[[1 2]
  [3 4]]]

(2, 2)
(1, 2, 2)
```

`np.squeeze`

从给定的数组的形状中删除一维的条目

```python
a = x = np.array(([1, 2], [3, 4]))
y = np.expand_dims(a, 0)
z = np.squeeze(y, 0)
[[1 2]
 [3 4]]

(2, 2)
```

**连接数组**

`np.concatenate((a1, a2, a3,..), axis)`

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.concatenate((a, b), axis = 0))
print(np.concatenate((a, b), axis = 1))

[[1 2]
 [3 4]
 [5 6]
 [7 8]]
[[1 2 5 6]
 [3 4 7 8]]
```

`np.stack(arrays, axis)` axis:返回数组中的轴，按照输入数组(a, b)当作一个数组的维度

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.stack((a, b), axis = 0))
print(np.stack((a, b), axis = 1))
print(np.stack((a, b), axis = 2))

[[[1 2]
  [3 4]]

 [[5 6]
  [7 8]]]

(2, 2, 2)

[[[1 2]
  [5 6]]

 [[3 4]
  [7 8]]]
(2, 2, 2)

[[[1 5]
  [2 6]]

 [[3 7]
  [4 8]]]

(2, 2, 2)
```

`np.hstack`:水平(horizontal)堆叠来生成数组

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.hstack((a, b)))

[[1 2 5 6]
 [3 4 7 8]]
```

`np.vstack`：垂直(vertical)堆叠来生成数组

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.vstack((a, b)))

[[1 2]
 [3 4]
 [5 6]
 [7 8]]
```

**分割数组**

`np.split(arr, axis)` : axis为0时在水平方向分割，axis为1时在垂直方向分割

```python
a = np.arange(9)
print(np.split(a, 3))  #分为三个大小相等的子数组
print(np.split(a, [4, 7])) #按数组的位置分割
```

`np.hsplit(arr, n)`按水平方向分割

`np.vsplit(arr, n)`按垂直方向分割

**数组元素的添加与删除**

`np.resize(arr, shape)`

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
b = np.resize(a, (3, 2))
```

`np.append(arr, values, axis)`：向数组追加元素, axis为0时，加在下边（列数要相同）； axis为1时， 加在右边（行数要相同）

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
b = np.append(a, [[7, 8, 9]], axis = 0)
c = np.append(a, [[5, 5, 5], [7, 8, 9]], axis = 1)
print(b)
print(c)
[[1 2 3]
 [4 5 6]
 [7 8 9]]

[[1 2 3 5 5 5]
 [4 5 6 7 8 9]]
```

`np.insert(arr, obj, values, axis)` obj: 在其之前插入值的索引

未传递axis参数，输出数组会被展开

传递axis参数，会广播值数组来匹配输入数组

`np.delete(arr, obj, axis)`与insert相似，未传递axis会被展开

`np.unique(arr, return_index, return_inverse, return_counts)`

arr: 输入数组，如果不是一维数组会被展开

return_index: 如果为True，返回新列表元素在旧列表中的位置（下标）， 并以列表存储

return_inverse: 如果为True, 返回旧列表元素在新列表中的位置（下标），并以列表存储

return_counts: 如果为True, 返回去重数组中的元素在原数组中的出现次数

##### 9、数学函数

`np.around(a, decimals)` decimals: 四舍五入，舍入的小数位数， 默认值为0

`np.floor(arr)`: 向下取整

`np.ceil(arr)`： 向上取整

##### 10、排序，条件筛选函数

`np.sort(arr, axis, kind, order)`

axis: 0为按列排序，1为按行排序

kind:默认为快速排序

`np.argsort(arr)`, 返回的是数值从小到大的索引值

`np.nonzero()`:返回输入数组中非零元素的索引

`np.where()`：返回输入数组中满足给定条件的元素的**索引****

```python
x = np.arange(9).reshape((3, 3))
y = np.where(x > 3)
print(x[y])
```

##### 11、随机数

随机整数， `random.randint(a, b)`，生成区间内的整数

随机小数， `np.random.randn(5)`，生成5个随机小数

0-1随机小数， `random.random()`，括号内不含参