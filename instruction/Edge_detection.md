# 边缘检测
常见的边缘检测算子：Roberts 、Sobel 、Prewitt、Laplacian、Log/Marr、Canny、Kirsch、Nevitia
## 1. 梯度计算
根据边缘检测算子模板对图片进行卷积就可以得到模板所对应的中心点的梯度幅值，所以根据不同的边缘检测算子模板，计算梯度分为不同的类型sobel，prewitt，roberts
## 1. Canny边缘检测
### 1.1 步骤
（1）高斯滤波去除噪声

（2）计算梯度幅值和方向

（3）非最大值抑制

（4）滞后阈值

    Ⅰ.如果某一像素位置的幅值超过 高 阈值, 该像素被保留为边缘像素。

    Ⅱ.如果某一像素位置的幅值小于 低 阈值, 该像素被排除。

    Ⅲ.如果某一像素位置的幅值在两个阈值之间,该像素仅仅在连接到一个高于 高 阈值的像素时被保留。

