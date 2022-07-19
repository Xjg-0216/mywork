### 

数据类型

python有6个数据类型：

* 数字(Number)
* 元组（tuple）
* 字典（dict）
* 字符串（string）





python中的数据类型可以分为**数字型**和**非数字型**

数字型：

* 整型（int）

* 浮点型(float)
* 布尔型（bool）
* 复数型（complex）

非数字型：

* 字符串
* 元组
* 列表
* 字典

在python中，所有的非数字型都支持以下特点：

1、都是序列，也可以理解为容器

2、取值[]

3、遍历 for in 

4、计算长度，最大/最小值，比较、删除

5、切片

6、连接 + ， 重复 *

#### 1、字典

字典可以存储**多种数据**， 是**无序**的对象集合

字典用{}定义， 键值对之间使用`,`分隔

键必须是唯一的，不能相同；值可以去任何数据类型，但**键**只能使用**字符串、数字或元组**

```python
xiaoming = {"name": "小明"， "age":18, "gender":True, "height": 1.75}
```

```python
#字典.keys() : 可以从字典中取出键， 组成一个列表
>>> xiaoming.keys()
>>> ['name', 'age', 'gender', 'height']

#字典.values(): 取出字典中所有值，组成一个列表
>>> xiaoming.values() 
>>> ['小明'， 18， True, 1.75]

#字典.items(): 返回键值对组成的元组
>>> xiaoming.items()
>>> ('name', '小明') ('age', 18) ('gender', True) ('height', 1.75)

#字典[key]: 找到对应key的value, 如果key不存在会报错keyerror
>>> xiaoming["name"]
>>> "小明"

#字典.get(key): 找到对应key的value， 如果key不存在会返回None

#del 字典[key]: 删除对应key的键值对， key不存在会报错

#字典.pop(key)： 弹出对应key的键值对，Key不存在会报错

#字典.popitem()：弹出最后一个键值对

#字典.clear()：清空字典

#字典[key] = value：如果key存在，修改其对应的value； 如果key不存在，新建键值对

#字典.setdefault(key, value)：如果key存在，其对应的value不改变；如果key不存在，新建键值对

#字典2.update(字典1)： 将字典1中的数据合并到字典2中
>>> xiaoming.update({"area": "China"})
>>> {'name': '小明', 'age': 18, 'gender': True, 'height': 1.75, 'area': 'China'}

#dict.fromkeys(): 为多个key赋相同的值返回新的字典

```

#### 2、列表

列表用[]定义，数据之间使用`,`分隔

列表的索引从0开始，索引又称下标

```python
name_list = ["zhangsan", "lisi", "wangwu"]

#name_list.append: 在name_list后面添加元素
>>> name_list.append("fengliu")
>>> ['zhangsan', 'lisi', 'wangwu', 'fengliu']

#name_list.count(数据):数据在name_list中出现的次数 
>>> name_list.count("lisi")
>>> 1

#name_list.insert(索引，数据):在指定索引上插入数据 
>>> name_list.insert(0, "zzz")
>>> ['zzz', 'zhangsan', 'lisi', 'wangwu']

#name_list.reverse(): 反转
>>>['wangwu', 'lisi', 'zhangsan']

#name_list.clear(): 清空列表

#name_list.extend(列表2):将列表2的数据追加到name_list
>>> name_list.extend([1, 2, 3])
>>> ['zhangsan', 'lisi', 'wangwu', 1, 2, 3]

#name_list.pop(i): 删除索引为数据

#name_list.sort(): 升序排序
#name_list.sort(reverse=True): 降序排序

#name_list.copy(): 列表复制

#name_list.index(数据): 从列表中找出某个值第一个匹配项的位置
>>> list = [1, 4, 7, 32, 2, 3, 0,  1]
>>> print(list.index(1))
>>> 0

#name_list.remove(数据):从列表中去除某个值第一个匹配项的位置
>>>list = [1, 4, 7, 32, 2, 3, 0,  1]
>>>.remove(1)
>>> [4, 7, 32, 2, 3, 0, 1]
```

#### 3、元组

元组与列表类似，不同之处在于元组的元素不可修改

用于存储一串信息，数据之间使用`,`分隔

元组用()定义

元组索引从0开始

**元组中只包含一个元素时， 需要在元素后面添加逗号**

```python
tuple = (1, 2 ,3 , 4, 5)

#tuple.count(元素)： 统计某个元素的个数
#tuple.index(元素)： 该元素第一次出现的索引
```

