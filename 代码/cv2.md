### cv2

**图像读取**

```python
import cv2
img = cv2.imread(path)  #读取RGB图像
img = cv2.imread(path, cv2.IMREAD_GRAYSCALE) # 读取灰度图像
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) # 颜色空间转换
```

**图像显示**

```python
cv2.imshow('image', img) #第一个参数是显示图像窗口的名称，第二个参数是要显示的图像，窗口大小自动调整为图片大小
cv2.waitKey(0) # 等待键盘输入，单位是毫秒，即等待指定的毫秒数看是否有键盘输入，若在等待时间内按下任意键则返回按键的ASCII码，程序继续运行。若没有按下任意键，超时返回-1。参数0表示为无限等待，不调用waitKey的话，窗口会一闪而逝，看不到显示的图片
cv2.destoryAllWindow() #销毁所有的窗口
```

**保存图像**

```python
cv2.imwrite(path, img)
```

### plt

```python
import matplotlib.pyplot as plt
```

```
plt.plot(x, y)
plt.show()
```

plt.figure()用来画图，自定义画布大小

```python
fig = plt.figure(num = 'name', figsize=(10, 3), dpi=75)
```



### 文本读写

`with`关键字

优点： 当子句体结束后文件会正确关闭，即使在某个时刻引发了异常

```python
with open("text.txt") as f:
    read_data = f.read()
f.close()
```

`f.close()`用来关闭文件并立即释放它使用的所有系统资源，如果你没有显式的关闭文件，python的垃圾回收器最终将销毁该对象并为你关闭打开的文件。

`read()`

`readline()`：从文件中读取整行数据，包括换行符`\n`,换行符留在字符串的末尾，如果文件不以换行符结尾 ，则在文件的最后一行省略，如果`f.readline()`返回一个空的字符串，则表示已经到达了文件末尾

`readlines()`：返回所有行的内容组成的列表

```python
f.write()
```

