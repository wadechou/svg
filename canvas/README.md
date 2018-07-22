#canvas基础教程
https://www.imooc.com/learn/476
https://www.imooc.com/learn/185
====

#游戏：
https://hiloteam.github.io/
http://spritejs.org/
http://createjs.com/   （https://aotu.io/notes/2017/07/19/createjs/）

#图表：
https://github.com/chartjs/Chart.js

#基础库：
http://fabricjs.com/



<!-- -------------------------------------------------------------------------------- -->
webGL（全写Web Graphics Library）是一种3D绘图标准。
WebGL 是一项使用JavaScript实现3D绘图的技术。无论canvas还是SVG都不能绘制3D图形。
WebGL 为HTML5 Canvas提供硬件3D加速渲染。因为原生的WebGL很复杂，我们经常会使用一些三方的库，如three.js等，这些库多数用于HTML5游戏开发。



canvas是使用JavaScript程序绘图(动态生成)，SVG是使用XML文档描述来绘图。
从这点来看：SVG更适合用来做动态交互，而且SVG绘图很容易编辑，只需要增加或移除相应的元素就可以了。
同时SVG是基于矢量的，所有它能够很好的处理图形大小的改变。Canvas是基于位图的图像，它不能够改变大小，只能缩放显示；所以说Canvas更适合用来实现类似于Flash能做的事情。


canvas是操作内存的，不是操作界面的
他是通过内存中的数据，以及数据的属性来做判断等。所以他的data都存在内容中。他的界面就是一张图。没有任何类似html的元素。


====
canvas是状态的绘制。
什么属性一直保持着，什么状态一直存在着。


绘制：
1、moveTo会重新定位开始点。

2、要改变其他状态，如颜色，width，也针对路径。有moreTo的作用
beginPath();表示清空上一个坐标点。此时可以用lineTo替换moveTo。

closePath绘制封闭的图形。同时closePath可以自动连接最后一个点到第一个点。


填充：
fill();
先fill再stroke这样描边的width不会减半。




矩形：
rect()
以下和rect的区别是不需要规划路径了。不需要beginPath();也不需要使用fill和stroke来执行绘制。
fillRect()
strokeRect()


lineCap:线段的帽子,只有起始点有有效

butt
round
square：也可以闭合路径，不会出现瑕疵。


lineJoin:线与线相接的处理。
miter，miterLimit
bevel
round




translate：应该回撤原点


针对路径的：保存并且恢复当前canvas绘图的状态，更方便的进行图形的变换操作，维护canvas绘图环境的安全性。与上下文有关。
save()
restrore()

scale()
所有属性都会scale


这些操作要先于fillRect等，要在路径绘制之前。
transform
setTransform




同时这些变换有时需要把中心点移动到需要的位置。
需要重新计算中心点。
context.translate(x + width/2, y + height/2);
context.fillRect(-0.5 * width, -0.5 * height);
