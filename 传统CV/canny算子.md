#### canny算子

图像边缘信息主要集中在高频段，通常说图像锐化或检测边缘，实质就是高频滤波。我们知道微分运算事求信号的变化率，具有加强高频分量的作用。在空域运算中来说，对图像的锐化就是计算微分。由于数字图像的离散信号，微分运算就变成计算差分或梯度。图像处理中有多种边缘检测（梯度）算子， 常用的包括`普通一阶差分`，` Robert算子（交叉差分）`， `Sobel算子`等等, 是基于寻找梯度强度，拉普拉斯算子（二阶差分）是基于过零点检测。通过计算梯度，设置阈值，得到边缘图像。

Canny算子求边缘点具体算法步骤如下：

1、将彩色图像转化为灰度图

2、用高斯滤波器平滑图像

3、用一阶偏导有限差分计算梯度幅值和方向

4、对梯度幅值进行非极大值抑制。

5、用双阈值算法检测和连接边缘。

Canny算子使用滞后阈值，滞后阈值需要两个阈值（高阈值和低阈值）， 若某一像素位置的幅值超过高阈值，该像素被保留为边缘像素； 若某一像素位置的幅值小于阈值，该像素被排除； 若某一像素位置的幅值在两个阈值之间，该像素仅仅在连接到一个高于高阈值的像素时被保留。