# pixelCGframewk
a pixel frame for Computer Graphics


- [x] drawArcWithBresenham
- bresenham画直线
- [x] ClipAlgorithm 
- 裁剪算法
- [x] polyhedronProjection
- 多面体的投影和旋转
- [x] scanLineToFillPolygon
- 多边形的扫描线填充
- [x] rubberInGDIplus
- 双缓冲技术实现橡皮筋技术
- [x] bezierCarveProj
- 绘制贝塞尔曲线
## THE DEETAILS
### drawArcWithBresenham

整体逻辑为：窗体初始化，画初始的像素格，默认长宽为原wenFrom的10个像素->点击像素格可以选择起点、终点，超过3个点时之使用最后两个点，前面的点被覆盖->点击相应按钮实现：画直线、画圆和清除。

一些说明：1，窗体上显示的终点作为画圆和画圆弧的圆心；
2，清除功能目前只清除画的线和弧段，并没有擦除选择点的坐标（不希望在画直线的时候加入太多if判断，例如擦除之后需要判断是否选择了点）；并且没有像老师展示的重新选择圆心时会擦除原先画的圆，而是仍然会保留，可以制作一些艺术组合图案。
3，目前没有处理超出画了方格区域外的点；
4，默认点击形成的起点和终点采用红色填充；算法画出的直线用蓝色填充；可以看出按照教材里的循环到k是“画”不到终点的（终点仍然为红色）；
5，退出功能可以通过点击右上角的X实现，因此不设单独的按钮；
6，代码中存在几种坐标系下的坐标；默认坐标指原点在窗体左上角的坐标；xy坐标系指原点在方格左下角的坐标系；像素点坐标是在xy坐标系下原来wsize个像素（默认为10）下为一个像素的坐标，winForm坐标指原来xy坐标系的坐标，例如winForm坐标点(203,127)对应的像素点坐标为（20,12）。

### ClipAlgorithm 
裁剪效果的算法
### polyhedronProjection
see at [here](https://github.com/QLWeilcf/pixelCGframewk/blob/master/polyhedronProjection/readme.md)
改变坐标系，初始化一些默认值，画坐标轴，初始化一个长方体，用默认的视点投影该长方体。交互上包括单选框、输入框和按钮；单选框和输入框都有初始值，代码会对输入值进行检查，单选框的值改变代码会应答，能直接看到效果，改变时传入的值为改变前的空间点坐标；按钮可以直接点击。输入框的值改变在点击按钮时生效。
-  点击投影按钮时采用的是默认的空间多面体，因此采用的点坐标不是在自动旋转中以及停止时的点，不会展示多面体转到某个位置时改变视点的效果。


