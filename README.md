# Image_Processing&&Opencv_Learing
##一、理论知识
###1.图像的高频分量和低频分量：
原来在信号处理中，从前一秒到后一秒，信号周期性变化的次数，就是频率；相应地，在数字图像处理中，从一个像素点到相邻的一个像素点，灰度值变化的多少，就是频率.
所谓高频分量，就是频率值高，就是像素之间灰度变化大，这通常对应着图像区域边缘等；而低频分量，就是频率值低，就是像素灰度之间灰度变化小，这通常是图像中稳定的区域，是在一个object的内部，同属于一个superpixel...
###2.滤波
高斯滤波为什么会滤掉高斯
高斯白噪声，噪点的数值比较大，当进行滤波的时候，会将一些比较大的值进行平滑输出，但是缺点就是，会把边缘的一些信息也平滑掉
平滑滤波主要包括：线性平滑滤波（方框滤波、均值滤波、高斯滤波等）、非线性平滑滤波（中值滤波、序统计滤波）。opencv中对应boxblur、blur、gaussianblur函数。
锐化滤波主要包括：线性锐化滤波（拉普拉斯算子、高频提升滤波）、非线性锐化滤波（基于梯度的锐化滤波、最大-最小锐化变换等）
###3.形态学
（1）膨胀：
对卷积核中的值取最大，相当于放大物体，因为物体的彩色像素点一般都不叫大，如果背景是黑色的话，会膨胀物体
（2）腐蚀：
对卷积核中的值取最大，相当于缩小物体，原理和膨胀相反
（3）开运算：
先腐蚀后膨胀
腐蚀会缩小物体，
消除高于其临近点的孤立点
开运算可以用来消除小物体、在纤细点处分离物体、平滑较大物体的边界的同时并不明显改变其面积。
（4）闭运算：
先膨胀后腐蚀
消除低于其临近点的孤立点
（5）形态学梯度：
膨胀-腐蚀，当处在边缘的时候，膨胀把数值变大，腐蚀把数值变小，会出现差值，表现出来的梯度
（6）顶帽：
原图-开运算图
从A中减去open（A）可以突出周围的区域更明亮的区域
（7）低帽：
闭运算图-原图
从close（A）中减去A可以突出A周围比较暗的区域