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

#### 4、字符串

```python
#9个判断类型
#string.isspace(): 是否包括空格
>>> string = "hfuerwgnfjdufhavh"
>>> string.isspace()
>>> False

#string.isalnum(): 如果string至少有一个字符并且所有字符全是字母或者数字返回True
#string.isalpha(): 如果string至少有一个字符并且所有字符都是字母则返回True
#string.isdecimal();string.isdigit(); string.isnumeric()：如果string只包含数字则返回True
#string.istitle(): 如果string是标题化，每个单词首字母大写，则返回True
#string.islower(): 如果stirng至少包含一个字符，并且所有的字符都是小写，返回True
#string.isupper(): 如果string至少包含一个字符，并且所有的字符都是大写，返回True

#7个查找和替换
# string.startswith(str): 检查string是否以str开头，是则返回True
# string.endswith(str):  检查string是否以str结尾，是则返回True
# string.find(str, start, end): 检查string在索引start到end中是否有str， 有则返回索引，否则返回-1
# string.rfind(str, start, end): 类似于find(), 只不过从右边开始查找
# string.index(str, start, end): 跟find()类似，不过找不到str会报错
# string.rindex(str, start, end): 跟index()类似，不过从右边开始查找
# string.replace(old_str, new_str): 把string中的old_str替换成new_str

#5个大小写转换
#string.capitalize() 把字符串的首字符大写
#string.title() 把字符串每个单词首字母大写
#string.lower()  转换string 中所有大写字符为小写
#string.upper()  转换string 中所有小写字符为大写
#string.swapcase() 翻转string 中的大小写

#3个文本对齐
#string.ljust(width)： 返回一个元字符串的左对齐，并使用空格填充至长度为width的新字符串
#string.rjust(width): 返回一个原字符串右对齐，并使用空格填充至长度为width的新字符串
#string.center(width): 返回一个原字符串居中，并使用空格填充至长度为width的新字符串

#3个去除空白字符
#string.lstrip(): 裁掉string左边开始的空白字符
#string.rstrip(): 裁掉string右边开始的空白字符
#string.strip(): 裁掉string左右两边的空白字符

#5个拆分和连接
#string.partition(str): 把字符串string分成一个3元素的元组， str前面，str, str后面
#string.rpartition(str): 类似于partition()方法，不过是从右边开始查找
#string.split(str): 以str为分隔符拆分string
#string.splitlines(): 按照行\r\n为分隔，返回一个包含各行作为元素的列表
#string.join(str): 以string作为分隔符，将str中所有元素合并为一个新的字符串
```

#### 69个内置函数

##### **常用的内置函数：**

abs(); sum(); float(); id(); hash(); int(); len(); list(); tuple(); set(); dict(); map(); max(); min(); pow(); range(); enumerate() ;sorted(); str(); super(); zip(); delattr(); setattr(); hasattr(); getattr(); isinstance(); reversed(); round(); next(); issubclass();exec(); eval()



1、abs

abs(x), 返回一个数的绝对值， 参数可以是整数或者浮点数，如果是复数，则返回它的模

```python
>>> abs(-0.2)
>>> 0.2
```

2、all()

all(iterable)， 如果iterable的**所有元素**均为True(或iterable为空)，则返回True

3、any()

any(iterable)，如果iterable的**任意元素**均为True(或iterable为空)，则返回True

4、ascii()

ascii(object)， 返回对象的纯ASCII表示形式

5、bin()

bin(x), 将一个整数转变为一个前缀为"0b"的二进制字符串

6、bool()

返回一个布尔值，True或者False, 如果没有参数，也是返回False

7、breakpoint()

略（不怎么用）

8、bytearray()

将数据转换成一个新字节的数组

9、bytes()

bytes()函数返回一个新的bytes对象， 该对象是一个[0, 255]区间内的整数不可变序列

10、callable()

callable(obj)， 用于检查一个对象是否可调用，可调用返回True， 否则返回False

另外，类是可调用的，调用类将返回一个新的实例

如果实例所属的类有`__call__()`方法，则也是可调用的

11、chr()

返回参数对应的ASCII字符

12、classmethod()

将方法转换为类方法，类方法将类作为隐式第一个参数接收，就像实例方法接收实例一样

classmethod修饰符对应的函数不需要实例化，不需要self参数，但第一个参数需要是表示自身类的cls参数，可以来调用类的属性，类的方法，实例化对象

```python
class B(object):
    num = 10
    def func1(self):
        print('self')
    @classmethod
    def func2(cls):
        print('func2')
        print(cls.num)
        cls().func1()
B.func2()  # 不需要实例化
```

13、compile()

compile()函数将一个字符串编译为字节代码

14、complex()

返回复数

```python
>>> complex(1, 2)
>>> (1 +2j)
```

15、delattr()

```python
delattr(obj, name)
```

实参是一个对象和一个字符串，该字符串必须是对象的某个属性。如果对象允许，**该函数将删除指定的属性**

delattr(car1, 'color')相当于del car1.color

16、hasattr()

hasattr():用于判断是否包含对应的属性

```python
hasattr(obj, name)
```

如果对象有该属性返回True， 否则返回False

17、getattr()

getattr()用于返回一个对象的属性值

```python
getattr(obj, name, default)
```

返回对象属性值，如果不存在返回默认值

18、setattr()

setattr()函数，用于设置属性值

```python
setattr(obj, name, value)
```

如果name属性存在则修改为value值， 如果不存在则设置name属性为value

```python
class Car:
    def __init__(self):
        pass
car1 = Car()
car1.color = 'red'
>>> hasattr(car1, 'color')
True
>>> hasattr(car1, 'colo')
False
>>> getattr(car1, 'color')
'red'
>>> setattr(car1, 'colo', 'yellow')
>>> getattr(car1, 'colo')
'yellow'
>>> delattr(car1, 'colo')
>>> hasattr(car1, 'colo')
False
```

19、dict()

创建一个新字典

20、dir()

返回当前范围内的变量，方法和定义的类型列表

21、divmod()

divmod(a, b)， 函数接收两个数字类型参数，返回一个包含商和余数的元组(a // b, a % b)

22、enumerate()

enumerate(iterable, start=0)， 返回一个枚举对象，iterable必须是一个序列或iterator, 或其他支持迭代的对象

23、eval()

执行一个字符串表达式，并返回表达式的值

24、exec()

执行字符串命令，可以带等号的字符串

25、filter()

```python
filter(function, iterable)
```

返回一个可迭代的filter对象，可以使用list()函数将其转化为列表

26、float()
将整数和字符串转换成浮点数

27、format()

```python
print("我叫{}, 今年{}岁".format("小明", 18))
print("我叫{name},今年{age}岁".format(name="小明", age=18))
```

28、forzenset()

返回一个冻结的集合，冻结后集合不能再添加或删除任何元素

29、globals()

返回包含当前作用域的全局变量的字典

30、hash()

返回对象obj的哈希值 

hash()函数可以应用于数字、字符串和对象，不能直接应用于list, set, dictionary

31、hex()

hex(x)， 将整数转化为以“0x”为前缀的小写十六进制字符串

32、id()

id(obj)， 返回该对象的内存地址

33、input()

接受一个标准输入数据，返回为string 类型

34、int()

将一个字符串或数字转换为整型

35、isinstance()

```python
isinstance(obj, classinfo)
```

isinstance()函数来判断一个对象是否是一个已知的类型，类似type()， isinstance()与type()区别： type()不会认为子类是一种父类类型，不考虑继承关系

36、issubclass()

```python
issubclass(class, classinfo)
```

issubclass()方法用于判断参数class是否是类型参数classinfo的子类

37、iter()

返回一个iterator对象

38、len()

返回对象的长度

39、list()

将元组或字符串转换成列表

40、locals()

会以字典类型返回当前位置的全部局部变量

41、map()

```python
#lambda匿名函数
lambda x, y: x*y: 函数输入是x和y， 输出是它们的积x*y
lambda *args: sum(args): 输入是任意个数的参数，输出是它们的和
```

```python
map(function, iterable)
```

返回一个将function应用于iterable中每一项并输出其结果的迭代器

42、max()

返回可迭代对象中最大的元素

43、memoryview()

返回给定参数的内存视图

44、min()
返回可迭代对象中最小的元素，或者返回两个及以上实参中最小的

45、next()

通过调用iterator的`__next__()`方法获取下一个元素，如果迭代器耗尽， 则返回给定的default， 如果没有默认值则触发stopIteration
46、object()

返回一个没有特征的新对象，object是所有类的基类，它具有所有python类实例的通用方法，这个函数不接受任何实参

47、oct()

返回整数的八进制表示形式

48、open()

open()函数用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出OSError

49、ord()
对单个字符的字符串，返回它的Unicode编码的整数

50、pow(base)

计算base的exp次方

51、print()

52、property()

作用是在新式类中返回属性值

53、range()

range()函数返回一个可迭代对象

54、repr()

返回包含一个对象的可打印表示形式的字符串

55、reversed()

返回给定序列值的反向迭代器

56、round()

返回number四舍五入的值

57、set()

创建一个无序不重复元素集， 删除重复数据，可以用于计算交集，差集，并集等

58、slice()

实现切片对象

59、sorted()

对所有可迭代的对象进行排序操作，默认为升序

60、str()

返回一个对象的string格式

61、sum()

求和

62、super()

用于调用父类的一个方法，用来解决多重继承问题

63、tuple()

将可迭代系列转换为元组

64、type()

传入一个参数时， 返回obj的类型，传入三个参数时，返回一个新的type对象

65、vars()

返回模块、类、实例或任何其它具有`__dict__`属性的对象的`__dict__`属性

66、zip()

用于将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的对象

67、import()

```python
__import__(name, globals=None, locals=None, fromlist=(), level=0)
```

import()函数用于动态加载类和函数

如果一个模块经常变化就可以使用import()来动态加载