
1、颜色和渐变
2、圆角
3、边框图片
4、盒子阴影
5、弹性盒子模型部分属性


颜色和渐变：

	颜色：HSL
		通过对色相(H)、饱和度(S)、明度(L)三个颜色通道的变化以及它们相互之间的叠
		加来得到各式各样的颜色。
	
		H：Hue(色调)。0(或360)表示红色，120表示绿色，240表示蓝色，也可取其他数值来指定颜色。
			取值为：0 - 360
		S：Saturation(饱和度)。取值为：0.0% - 100.0%
		L：Lightness(亮度)。取值为：0.0% - 100.0%
	
	HSLA
		此色彩模式与HSL相同，只是在HSL模式上新增了Alpha透明度
		取值：
			H：Hue(色调)。0(或360)表示红色，120表示绿色，240表示蓝色，也可取其他数值
				来指定颜色。取值为：0 - 360
			S：Saturation(饱和度)。取值为：0.0% - 100.0%
			L：Lightness(亮度)。取值为：0.0% - 100.0%
			A：Alpha透明度。取值0~1之间。
	
	opacity：不透明度
	rgba: 不透明度


​	
渐变：
线性渐变和径向渐变

linear-gradient() 线性渐变
	参数：
		to left、to right、to bottom、to top、to left top、to left bottom...
		angle
		color
		
	重复径向渐变
		repeating-linear-gradient()
radial-gradient() 径向渐变


2.圆角
border-radius:
	可以分别设置四个角也可以使用简写：
		boder-top-left-radius: 左上
		border-top-right-radius:右上
		border-bottom-right-radius:
		border-bottom-left-riadus:
	border-radius：可以设置一个值到四个值。
		顺序：
			1个值：四个角
			2个值: 左上右下 右上左下
			三个值:  左上  右上左下  右下 
			四个值: 左上 右上  右下  左下	
	
​		
3. border-image 边框图片
  目前只有IE11以上才支持。

  border-image 是一个简写值，分别具有以下的属性：
  	border-image-source	图片地址
  	border-image-slice   图片切片
  	border-image-width  图片宽度
  	border-image-outset  图片外凸
  	border-image-repeat  图片重复 

  border-image-slice图像进行切片处理。
  	当进行图像切片后，会将图片切成四个边四个角以及一个中间区域。
  	
  	值：
  		number | 百分比 {1,4}
  border-image-width 图片宽度
  	值：
  		length| number | 百分比{1,4}
  border-image-outset 图像外凸
  border-image-repeat 图像重复

4. 盒子阴影
  box-shadow:
  h-shadow v-shadow blue spread color inset;

  h-shadow 水平阴影的位置 允许负值
  v-shadow 垂直阴影的位置 允许负值
  blur: 模糊值
  spread:阴影的大小
  color :颜色
  inset :内部阴影

5. 弹性盒子模型

盒子模型与怪异盒子模型
什么是弹性盒子模型
旧版本弹性盒子模型简单介绍
新版本弹性盒子模型


怪异盒子模型：
	设置的宽度和高度就是元素在网页中实际占据的宽度和高度。
	开启怪异盒子模型：
		box-sizing:border-box|content-box
	
弹性盒子模型核心概念：
	主轴
	侧轴
	弹性容器
	弹性子元素
	
弹性容器专用属性：
flex-direction:
	作用：弹性容器中子元素的排列方式(主轴排列方式)【子元素在主轴上的排列方式】
	属性：
		row:默认在一行排列
		row-reverse:反转横向排列（右对齐，从后往前排，最后一项排在最前面。）
		column：纵向排列。
		column-reverse：反转纵向排列，从下往上排，最后一项排在最上面
	
flex-wrap:
	作用:设置弹性盒子的子元素超出父容器时是否换行 
	属性值：
		nowrap: 默认值。规定元素不拆行或不拆列。
		wrap:规定元素在必要的时候拆行或拆列。
		wrap-reverse:规定元素在必要的时候拆行或拆列，但是以相反的顺序。
	
flex-flow: flex-direction和flex-wrap的缩写

align-item:
	作用:设置弹性盒子元素在侧轴（纵轴）方向上的对齐方式
	属性值：
		flex-start：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴起始边界。
        flex-end：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴结束边界。
        center：弹性盒子元素在该行的侧轴（纵轴）上居中放置。（如果该行的尺寸小于弹性盒子元素的尺寸，则会向两个方向溢出相同的长度）。
        baseline：如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。

align-content:
	作用:修改 flex-wrap 属性的行为，类似 align-items, 但不是设置子元素对齐，
			而是设置行对齐(行与行的对其方式)
	属性:
		flex-start没有行间距
		flex-end底对齐没有行间距
		center居中没有行间距
		space-between两端对齐，中间自动分配
		space-around自动分配距离

justify-content:
	作用:设置弹性盒子元素在主轴（横轴）方向上的对齐方式
	属性：
		flex-start默认，顶端对齐
        flex-end末端对齐
        center居中对齐
        space-between两端对齐，中间自动分配
        space-around自动分配距离

------

弹性子元素属性
多列布局
响应式布局概念
媒体查询
移动端布局

1.弹性子元素相关属性：
	order：设置弹性盒子的子元素排列顺序。 number排序优先级，数字越大越往后排，默认为0，支持负数。
    flex-grow:设置或检索弹性盒子元素的扩展比率。
    flex-shrink:指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值。
    flex-basis:用于设置或检索弹性盒伸缩基准值。
    flex:设置弹性盒子的子元素如何分配空间。
    align-self:在弹性子元素上使用。覆盖容器的 align-items 属性。

order:设置弹性盒子的子元素排列顺序。 number排序优先级，数字越大越往后排，默认为0，支持负数。

flex-grow:设置或检索弹性盒子元素的扩展比率。
	参数：
	 <integer>：一个数字，规定项目将相对于其他灵活的项目进行扩展的量。默认值是 0。
	瓜分容器的剩余空间。
	什么是剩余空间？
		假设父元素的宽度是500px，
		有三个子元素，每个宽度是100，那么剩余空间就是500 - 100 * 3 = 200。
		而flex-grow就是用来瓜分剩余空间的。
		例如第一个盒子属性为flex-grow:1;那么剩余空间就会被分成一份，第一个盒子额外的占据了这一份。
		如果这个时候第二个盒子flex-grow:2;那么此时剩余空间就被分成三分，第一个盒子占一份，第二个盒子占两份。
		
​		
flex-basis:用于设置或检索弹性盒伸缩基准值。
	参数：<integer>：一个长度单位或者一个百分比，规定元素的初始长度。
	auto：默认值。长度等于元素的长度。如果该项目未指定长度，则长度将根据内容决定。
	
	flex-basis是width的替代品。如果子元素设置了flex-basis或者width，那么在分配空间之前，就会跟父容器预约这么多
	的空间，然后剩下的才归到剩余空间，然后父容器再把剩余空间分配给flex-grow的容器。如果同时设置了flex-basis
	和width，那么width的属性就会被覆盖，也就是说flex-basis的优先级比width高。


​	 
flex-shrink:指定了 flex 元素的收缩规则。
    参数：<integer>：一个数字，规定项目将相对于其他灵活的项目进行收缩的量。默认值是 1。

    当父容器的剩余空间为0的时候，并且默认处于非换行状态的情况下，子元素是没有办法利用弹性容器的剩余空间
    进行扩展的。
    如果如容器的剩余宽度为负数的情况下(子元素的宽度之和大于父容器的宽度)，那么子元素就会被收缩。
    收缩的比例为1:1.
    例如，一个弹性容器中有三个子元素，那么他们的收缩比例就为1:1:1.
    如果这个时候，第一个子元素设置了flex-shrink:2;那么我们就会发现，这个元素比其他两个元素收缩的幅度更大。
    同时呢，因为第一个子元素空间的更多收缩，所以第二个和第三个元素就会获得更多的空间。
    我们假设第二个和第三个盒子收缩比例为x1,那么第一个盒子的收缩比例就为x2.
    
    举个例子：
    
    父元素 500px。三个子元素分别设置为 150px，200px，300px。
    
    三个子元素的 flex-shrink 的值分别为 1，2，3。
    
    首先，计算子元素溢出多少：150 + 200 + 300 - 500 = -150px。
    
    那这 -150px 将由三个元素的分别收缩一定的量来弥补。
    
    具体的计算方式为：每个元素收缩的权重为其 flex-shrink 乘以其宽度。
    
    所以总权重为 1 * 150 + 2 * 200 + 3 * 300 = 1450
        总权重: 收缩比 * 宽度 之和
    三个元素分别收缩：
    溢出值 * 收缩比  * width / 总权重 = 收缩的宽度
    150 * 1(flex-shrink) * 150(width) / 1450 = -15.5
    150 * 2(flex-shrink) * 200(width) / 1450 = -41.4
    150 * 3(flex-shrink) * 300(width) / 1450 = -93.1
    三个元素的最终宽度分别为：
    
    150 - 15.5 = 134.5
    200 - 41.4 = 158.6
    300 - 93.1 = 206.9
    同样，当所有元素的 flex-shrink 之和小于 1 时，计算方式也会有所不同：
    
    此时，并不会收缩所有的空间，而只会收缩 flex-shrink 之和相对于 1 的比例的空间。
    
    还是上面的例子，但是 flex-shrink 分别改为 0.1，0.2，0.3。
    
    于是总权重为 145（正好缩小 10 倍，略去计算公式）。
    
    三个元素收缩总和并不是 150px，而是只会收缩 150px 的 (0.1 + 0.2 + 0.3) / 1 即 60% 的空间：90px。
    
    每个元素收缩的空间为：
    
    90 * 0.1(flex-shrink) * 150(width) / 145 = 9.31
    90 * 0.2(flex-shrink) * 200(width) / 145 = 24.83
    90 * 0.3(flex-shrink) * 300(width) / 145 = 55.86
    三个元素的最终宽度分别为：
    
    150 - 9.31 = 140.69
    200 - 24.83 = 175.17
    300 - 55.86 = 244.14




flex:设置弹性盒子的子元素如何分配空间。
        flex 属性用于设置或检索弹性盒模型对象的子元素如何分配空间。

        flex 属性是 flex-grow、flex-shrink 和 flex-basis 属性的简写属性。
        详情参阅flex缩写文档

align-self:在弹性子元素上使用。覆盖容器的 align-items 属性。

	值与容器属性一样，只是这个是单独的设置某个元素。

简介：
flex是flex-grow,flex-shrink和flex-basis的缩写，flex属性值可以只指定一个属性的值，而另外的属性值采
用各自在flex属性中的的初始值，但是有一点要注意的是：flex属性中flex-grow和flex-basis的初始值和它们原始
的默认值不同，至于为什么不同，mdn中有明确的说过这样的设计是为了让「flex」缩写在最常见的情景下比较好用。



flex中对应各属性的初始值：

flex-grow
  flex-grow用于设置各item项按对应比例划分剩余空间，若flex中没有指定flex-grow,则相当于设置了
    flex-grow:1

flex-shrink
  flex-shrink用于设置item的总和超出容器空间时，各item的收缩比例，若flex中没有指定flex-shrink,
    则等同于设置了flex-shrink:1


flex-basis
  flex-basis用于设置各item项的伸缩基准值，可以取值为长度或百分比，如果flex中省略了该属性，则相当
    于设置了flex-basis:0.

flex的不同取值
  flex的值的完整写法是[<flex-grow> <flex-shrink> <flex-basis>],不过它的取值还有可能是单个数字
    或者单个百分比等，不同种类的取值所表示的意思是大有不同的。

flex值为none
  当flex为none时,等同于flex: 0 0 auto;

flex值为auto
  当flex为auto时，等同于flex: 1 1 auto;

flex值为一个非负数字
  当flex取值为一个数字，则该数字是设置的flex-grow值，其它两个属性用初始值，如flex:1时，
    等同于flex: 1 1 0%

flex值为两个非负数字
  当flex取值为2个数字时，相当于设置的flex-grow和flex-shrink值，flex-basis取值为初始值，
    如flex:1 0时，等同于flex: 1 0 0%

flex值为一个数字和一个长度或百分比时
  当flex取值为1个数字和1个长度或百分比时，设置的是flex-grow和flex-basis的值，flex-shrink值
    时初始值，如flex:1 20%,等同于flex: 1 1 20%

-------------------------------------------------------------------------------
2. 多列布局
    多列布局.xmind

--------------------------------------------------------------------------------
3. 响应式布局概念
  3.1 相关人物介绍：
  伊桑·马科特（Ethan Marcotte）在2010年首先提出了响应式网页设计（RWD,Responsive Web Design）这个术语。
  在他的一篇文章《Responsive Web Design · An A List Apart Article》中他将已有的三种发开技巧（弹性
  图片，弹性网格布局，媒体与媒体查询） 进行了整合，命名为响应式网页设计。
  那什么才是真正的响应式设计？马科特说，真正的响应式设计方法不仅仅是根据可视区域大小而改变网页布局，而是要
  从整体上颠覆当前网页的设计方法，是针对任意设备的网页内容进行完美布局的一种显示机制。

3.2 响应式网页浏览
    了解响应式网页的特性

3.3 当今流行的网页布局方案
固定布局：以像素作为页面的基本单位，不管设备屏幕及浏览器宽度，只设计一套尺寸；

可切换的固定布局：同样以像素作为页面单位，参考主流设备尺寸，设计几套不同宽度的布局。通过识别的屏幕尺寸或
    浏览器宽度，选择最合适的那套宽度布局；

响应式布局：对页面进行响应式的设计实现，需要对相同内容进行不同宽度的布局设计，有两种方式：pc优先（从pc
端开始向下设计）；移动优先（从移动端向上设计）；无论基于那种模式的设计，要兼容所有设备，布局响应时不
可避免地需要对模块布局做一些变化（发生布局改变的临界点称之为断点）。

弹性布局：以百分比作为页面的基本单位，可以适应一定范围内所有尺寸的设备屏幕及浏览器宽度，并能完美利用有效空
    间展现最佳效果；

混合布局：同弹性布局类似，可以适应一定范围内所有尺寸的设备屏幕及浏览器宽度，并能完美利用有效空间展现最佳效果；
    只是混合像素、和百分比两种单位作为页面单位。

3.4 响应式布局的优缺点
设计特点：
    面对不同分辨率设备灵活性强
    能够快捷解决多设备显示适应问题
缺点：
    兼容各种设备工作量大，效率低下
    代码累赘，会出现隐藏无用的元素，加载时间加长
    其实这是一种折中性质的设计解决方案，多方面因素影响而达不到最佳效果
    一定程度上改变了网站原有的布局结构，会出现用户混淆的情况

3.5 开发响应式网页的前期准备

3.5.1 Meta标签的设置
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0,minimum-scale=1.0,  user-scalable=no">
    这段代码的几个参数解释：
    width = device-width：宽度等于当前设备的宽度
    initial-scale： 初始的缩放比例（默认设置为1.0）
    minimum-scale：允许用户缩放到的最小比例（默认设置为1.0）
    maximum-scale：允许用户缩放到的最大比例（默认设置为1.0）
    user-scalable：用户是否可以手动缩放（默认设置为no，因为我们不希望用户放大缩小页面）


3.5.2 meta标签其他可选设置

H5页面窗口自动调整到设备宽度，并禁止用户缩放页面
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no" />
忽略将页面中的数字识别为电话号码
<meta name="format-detection" content="telephone=no" />
忽略Android平台中对邮箱地址的识别
<meta name="format-detection" content="email=no" />
当网站添加到主屏幕快速启动方式，可隐藏地址栏，仅针对ios的safari
<meta name="apple-mobile-web-app-capable" content="yes" />
<!-- ios7.0版本以后，safari上已看不到效果 -->
将网站添加到主屏幕快速启动方式，仅针对ios的safari顶端状态条的样式
<meta name="apple-mobile-web-app-status-bar-style" content="black" />

3.5.3 rem 和 vw/vh
rem是以html根元素的字体大小为参考。
默认情况下，1rem = 16px，此时html相当于font-size:100%。

vh|vw这两个单位，以视口为参考。
视口单位中的“视口”，桌面端指的是浏览器的可视区域；移动端指的就是Viewport中的Layout Viewport。

    1vw等于视口宽度的1%。
    1vh等于视口高度的1%。
    Tip：并且会随着视口的变化而变化。

3.5.4 什么是断点？
断点，响应式网页发生变化的临界点。


3.5.5 什么是媒体查询，响应式网页与媒体查询的关系
媒体查询是css当中的一种技术，通过这种技术可以判断用户的浏览器宽度，类型，以及横屏还是竖屏等。

响应式网页的实现方式有很多，主流方式是通过媒体查询的形式来实现响应式网页。

3.5.6 媒体查询特性
媒体查询可以让我们根据设备显示器的特性（如视口宽度、屏幕比例、设备方向：横向或纵向）为其设定CSS样式，
媒体查询由媒体类型和一个或多个检测媒体特性的条件表达式组成。媒体查询中可用于检测的媒体特性有 width 、
height 和 color （等）。使用媒体查询，可以在不改变页面内容的情况下，为特定的一些输出设备定制显示效果。

3.5.7 媒体查询基本语法
@media 媒体类型  关键字 (条件1) 关键字 (条件2) ... {
    css code
}

常用媒体类型：
    all     所有设备
    aural    听觉设备
    braille   点字触碰设备
    print    打印
    tty      打字机设备
    tv      电视机等设备
    screen  显示器、笔记本、电脑等设备
    ...

    上述的设备有很多，只是简单的陈述几种，但是我们常用的设备只有all和screen

关键字：
    and 并且 和
    not 否定、排除
    only 限定

条件：
    min-width:400px

媒体查询语法示例:
    @media all (min-width:480px) {
        html {
            background:red;
        }
    }

    上述示例表示当用户设备屏幕处于最小宽度为480px以上的时候，网页的背景颜色为红色
    
    /* 竖屏 */
    @media screen and (orientation:portrait) {对应样式}
    
    /* 横屏 */
    @media screen and (orientation:landscape){对应样式}

3.5.8 常用断点值

    320px
    480px
    768px
    1024px

3.5.9 css2中媒体查询的用法

其实并不是只有CSS3才支持Media的用法，早在CSS2开始就已经支持Media，具体用法，就是在HTML页面的head标签中插入如下的一段代码
<link rel="stylesheet" type="text/css" media="screen" href="style.css">;
想知道现在的移动设备是不是纵向放置的显示屏，可以这样写：
<link rel=“stylesheet” type=“text/css” media=“screen and  (orientation:portrait)”  	href="style.css">
orientation:portrait：指定输出设备中的页面可见区域高度大于或等于宽度
landscape：除portrait值情况外，都是landscape
第一段的代码也用CSS2来实现，让它一样可以让页面宽度小于960的执行指定的样式文件：
<link rel="stylesheet" type="text/css" media="screen and (max-width:960px)" href="style.css">

3.5.10 移动端优先和pc端优先

在开发响应式网页的时候，我们有两种选择，一种是从移动端开始开发然后逐渐升级到pc，这种方式叫做移动端优先
pc端优先则正好相反。

# Css3 动画课程



## Transition 过渡效果

**兼容性**

`ie10+` 、`谷歌`、`火狐`、`欧朋`、`safari`.

**相关属性**

### transition 简写属性

### transition-property 规定用于参与css过渡的具体属性

​	**transition-property 设置的是具体属性，如果没有在本条属性中设置某个属性参与过渡，那么没有参与的属性就不会具有过渡效果。**

​	**如果没有设置transition-property 属性，那么标签的所有属性默认都会参与到过渡效果中来。**

​	**如果在设置transition-property属性的时候，想要让所有的属性都参与过渡，可以设置为*all***。

​	**如果在设置的时候，不想让任何属性参与进过渡效果，但是还必须设置这个属性，那么就可以将属性值设置为*none。***

* 语法:
  * transition-property 具体参数：
  * none 没有过渡效果
  * all 全部属性参与过渡
  * property 具体属性值，每一个属性值之间使用逗号分隔。



> transition-property : none | all | property 



```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            transition-property: all;
            transition-duration: 1s;
        }
        p:hover {
            width: 3000px;
            height: 4000px;
            background-color: pink;
        }
    </style>
</head>
<body>
    <p>

    </p>
</body>
</html>
```





### transition-duration 过渡时间/过渡需要使用的具体时间 秒|毫秒  s||ms

### transition-timing-function 规定过渡效果的时间曲线  ，默认值是`ease`。

> 贝塞尔曲线的示例网址:`http://cubic-bezier.com/#.26,.84,.87,.11`。

属性值：

1.  cubic-bezier 后面设置的是具体的贝塞尔曲线的值
2.  linear 规定以相同的速度从开始到结束 (等于 cubic-bezier(0,0,1,1))
3.  ease 规定慢速开始，然后加快，最后慢速结束（cubic-bezier(0.25,0.1,0.25,1)）。
4.  ease-in   规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)） -- 加速。
5.  ease-out  慢速结束过渡效果 等于 cubic-bezier(0,0,0.58,1)  -- 减速
6.  ease-in-out  规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)） 



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            transition-property: all;
            transition-duration: 10s;
            /*transition-timing-function: cubic-bezier(.17,.67,.87,.11);*/
            /*transition-timing-function: linear;*/
            /*transition-timing-function: ease;*/
            transition-timing-function: ease-in;
        }
        p:hover {
            width: 300px;
            height: 400px;
            background-color: pink;
        }
    </style>
</head>
<body>
    <p>

    </p>
</body>
</html>
```

### transition-delay 延迟 

**作用:在指定的时间之后再来执行变化效果。**

单位:s|ms



> transition: property duration timing-function delay;
>
> *如果使用简写的话，不去设置的具体属性都会采用默认值的形式。*



我们在实际设置延迟的时候，也可以给具体的某个属性设置延迟。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightpink;
            transition:1s width 2s,2s height ,3s background-color;
        }
        p:hover {
            width: 300px;
            height: 300px;
            background-color: red;
        }
    </style>
</head>
<body>
    <p>

    </p>
</body>
</html>
```



过渡示例:

**手风琴**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>手风琴</title>
    <style>
        body {
            margin:0;
            padding:0;
            background-color: #f7f7f7;
        }
        h3 {
            margin:0;
            padding:0;
        }
        .box {
            width: 500px;
            margin:0 auto;
        }

        .list h3 {
            height: 35px;
            line-height:35px;
            padding-left: 30px;
            border-bottom:2px solid #690;
            font-size:14px;
            color: #fff;
            background-color: #369;
            transition: all 0.3s ease 0s;
        }
        .list .pictxt {
            height: 0;
            background-color: lightblue;
            transition: all 0.3s ease 0s;
        }
        .list:hover  h3 {
            background-color: #036;
        }
        .list:hover .pictxt{
            height: 150px;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="list">
            <h3>今日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>昨日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>前日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>去年新闻</h3>
            <div class="pictxt"></div>
        </div>
    </div>
</body>
</html>
```



## CSS3 2D



**相关属性**:

* transform : 2d/3d之间的转换
* transform-origin : 更改元素的基点  



相关属性值: *位移/旋转/缩放/倾斜*

* translate(x,y)   沿着x y 移动元素/ translateX(n)  translateY(n)    
* scale(x,y)  缩放  更改元素的宽度和高度 ,将宽度改为原来的x倍，高度改为原来的y倍 / scaleX(n) 更改宽度  scaleY(n)  更改高度
* rotate(angle)  旋转 
* skew(x-angle,y-angle)  定义2D 倾斜转换 沿着x轴和y轴  / skewX(angle) 沿着x轴转换  skewY(angle) 沿着y轴



**translate(x,y)**  x表示沿着x轴位移的距离， y 表示沿着y轴位移的距离

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .box {
            width: 600px;
            height: 300px;
            border: 2px solid orange;
            margin: 0 auto;
        }
        .box .d1 {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            margin:0 auto;
            transition: 2s;
        }
        .box:hover .d1 {
            transform: translate(100px,100px);
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="d1"></div>
    </div>
</body>
</html>
```



**scale(x,y)**  x表示宽度的倍数  y表示高度的倍数 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>scale</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: lightpink;
            transition: 2s;
        }
        div:hover {
            transform: scale(0.5,0.5);
        }
    </style>
</head>
<body>
    <div>

    </div>
</body>
</html>
```

**rotate(angle)**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>rotate</title>
    <style>
        .d1 {
            width: 100px;
            height: 100px;
            background-color: deepskyblue;
            border-left: 2px solid lawngreen;
            border-right: 2px solid gold;
            border-top: 2px solid palevioletred;
            border-bottom: 2px solid royalblue;
            transition: 5s;
            border-radius: 50%;
        }
        .d1:hover {
            transform: rotate(1080deg);
        }
    </style>
</head>
<body>
    <div class="d1">指向谁谁乌龟-></div>
</body>
</html>
```

**skew(x-angle,y-angle)**  倾斜/斜切

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>skew</title>
    <style>
        .playhappy {
            width: 100px;
            height: 100px;
            background-color: aquamarine;
            margin:100px auto;
            /*transition: 2s;*/

        }
        .playhappy:hover {
            transform: skew(0deg,10deg);
        }
    </style>
</head>
<body>
    <div class="playhappy"></div>
</body>
</html>
```



**transform-origin : 更改元素的基点**![1553484551358](C:\Users\liujunhang\AppData\Roaming\Typora\typora-user-images\1553484551358.png)

**语法:**

transform-origin:(x轴值,y轴值)

* x轴: left | center | right | length | % 
* y轴: top | center | bottom | length | %

示例:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>盘它</title>
    <style>
        img {
            width: 300px;
            height: 300px;
        }
        .anim_image {
            transition: all 1s ease-in-out;
            cursor: pointer;
        }
        .anim_image_top {
            position: absolute;
            transform: scale(0,0);
        }
        .anim_box:hover .anim_image_top {
            transform: scale(1,1);
            transform-origin: top right;
        }
        .anim_box:hover .anim_image_bottom {
            transform: scale(0,0);
            transform-origin: bottom left;
        }
    </style>
</head>
<body>
    <div class="anim_box">
        <img src="./images/photo3.jpg" class="anim_image anim_image_top">
        <img src="./images/photo4.jpg" class="anim_image anim_image_bottom">
    </div>
</body>
</html>
```







## CSS3 3D

**相关属性**:

- transform:2d/3d之间的转换
- transform-origin:更改元素的基点
- transform-style:flat|preserve-3d 开启3d空间
- perspective    景深,一般值的范围在900px-1200px ,景深的值最好不要太夸张
- perspective-origin 景深基点
- backface-visibibility   背面隐藏



相关属性值：

- translateX | translateY | translateZ | translate3d(x,y,z)
- scaleX | scaleY | scaleZ | scale3d()
- rotateX(angle) | rotateY(angle) | rotateZ(angle)



## 景深

> 更多的时候是用在父元素的身上。

示例:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        section {
            width: 400px;
            height: 400px;
            border: 1px solid red;
            margin: 100px auto;
            /*一定要设置在父元素的身上*/
            perspective: 300px;
        }
        div {
            width: 100px;
            height: 100px;
            background-color: lightblue;
            transition: 1s;
        }

        section:hover div {
            transform: rotateX(45deg);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```



## 开启3D空间

**transform-style:flat|preserve-3d 开启3d空间**

当属性值为`flat`的时候，网页是默认为`2d`空间的。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        section {
            width: 600px;
            height: 400px;
            border: 2px solid lightcoral;
            margin: 200px auto;
            background-color: lightblue;
            /*如果没有开启3d空间，那么效果就只是一个平面*/
            transform-style: preserve-3d;
            perspective: 400px;
            transition: 2s;
        }

        section div {
            width: 100px;
            height: 100px;
            background-color: lightgreen;
            transition: 2s;
        }
        section:hover {
            transform:rotateY(85deg);
        }
        section:hover div {
            transform: translateZ(100px);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```

### 示例：正方体

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        * {
            margin:0;
            padding:0;
        }
        ul,li {
            list-style:none;
        }

        ul {
            width: 200px;
            height: 200px;
            margin:100px auto;
            position: relative;
            transition: 12s;
            transform-style: preserve-3d;
            /*perspective: 400px;*/
            /*transform: rotateY(45deg);*/
        }

        ul li  {
            width: 100%;
            height: 100%;
            text-align: center;
            line-height:200px;
            font-weight: bold;
            font-size: 40px;
            position: absolute;
            /*backface-visibility:hidden;*/
        }
        ul li:nth-of-type(1) {
            background-color: rgba(0,0,111,.4);
            transform: rotateX(0deg) translateZ(100px);
        }

        ul li:nth-of-type(2) {
            background-color: rgba(100,201,111,.4);
            transform: rotateX(-90deg) translateZ(100px);
        }

        ul li:nth-of-type(3) {
            background-color: rgba(200,10,90,.4);
            transform: rotateX(-180deg) translateZ(100px);
        }

        ul li:nth-of-type(4) {
            background-color:  rgba(66,120,99,.4);
            transform: rotateX(-270deg) translateZ(100px);
        }
        ul li:nth-of-type(5) {
            background-color: rgba(140,200,140,.4);
            transform: rotateY(-90deg) translateZ(100px);
        }

        ul li:nth-of-type(6) {
            background-color: rgba(190,90,190,.4);
            transform: rotateY(90deg) translateZ(100px);
        }

        ul:hover {
            transform: rotateX(360deg) rotateY(360deg) scale3d(4,4,4);
        }
    </style>
</head>
<body>
    <ul>
        <li>第1个面</li>
        <li>第2个面</li>
        <li>第3个面</li>
        <li>第4个面</li>
        <li>第5个面</li>
        <li>第6个面</li>
    </ul>
</body>
</html>
~~~

## rotate3d(x,y,z,a)

x：是一个0到１之间的数值，主要用来描述元素围绕X轴旋转的矢量值；
y：是一个０到１之间的数值，主要用来描述元素围绕Y轴旋转的矢量值；
z：是一个０到１之间的数值，主要用来描述元素围绕Z轴旋转的矢量值；
a：是一个角度值，主要用来指定元素在3D空间旋转的角度，如果其值为正值，元素顺时针旋转，反之元素逆时针旋转。 





## **3D缩放**：

CSS3 3D变形中的缩放主要有scaleZ()和scale3d()两种函数，当scale3d()中X轴和Y轴同时为1，即scale3d(1,1,sz)，其效果等同于scaleZ(sz)。通过使用3D缩放函数，可以让元素在Z轴上按比例缩放。默认值为１，当值大于１时，元素放大，反之小于１大于0.01时，元素缩小。

*scale3d(sx,sy,sz)*

 sx：横向缩放比例；
 sy：纵向缩放比例；
 sz：Z轴缩放比例；

*scaleZ(s)*

s：指定元素每个点在Z轴的比例。 
**注：scaleZ()和scale3d()函数单独使用时没有任何效果，需要配合其他的变形函数一起使用才会有效果**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        section {
            width: 400px;
            height: 400px;
            border: 2px solid lightseagreen;
            perspective: 300px;
            transform-style: preserve-3d;
        }
        div {
            width: 100px;
            height: 100px;
            background-color: lime;
            transition: 8s;
        }
        section:hover div {
            transform:rotateX(720deg) scale3d(1.2,2.1,3);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```

## translate3d

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .stage {
            width: 300px;
            height: 300px;
            float: left;
            margin:15px;
            position: relative;
            background: url("./img/bg.jpg") repeat center center;
            perspective: 1200px;
        }

        .container {
            position: absolute;
            top:20%;
            left:50%;
            transform-style: preserve-3d;

        }

        .container img {
            position: absolute;
            margin-left:-70px;
            margin-right:-100px;
        }

        .container img:nth-child(1) {
            z-index:1;
            opacity: .6;
        }

        .s1 img:nth-child(2) {
            z-index:2;
            transform:translate3d(30px,30px,200px);
        }


        .s2 img:nth-child(2) {
            z-index: 2;
            transform: translate3d(30px,30px,-200px);
        }



    </style>
</head>
<body>
<div class="stage s1">
    <div class="container">
        <img src="./img/k2.png" alt="" width="70" height="100">
        <img src="./img/k2.png" alt="" width="70" height="100">
    </div>
</div>

<div class="stage s2">
    <div class="container">
        <img src="./img/k2.png" alt="" width="70" height="100">
        <img src="./img/k2.png" alt="" width="70" height="100">
    </div>
</div>


</body>
</html>
```



## 动画 animation

Animation是一个简写属性，包含以下内容：

1、Animation-name    调用关键帧

2、Animation-duration   设置完成时间

3、Animation-timing-function   动画的速度曲线

4、Animation –delay                   延迟

5、Animation-iteration-count   动画应该播放的次数

​	N  设置播放次数    infinite   无限次播放  

6、Animation-direction        规定是否该轮流反向播放动画

​	Normal   alternate   动画应该轮流反向播放

7、Animation-play-state              暂停/运行

​	Paused  暂停

​	Running  运行

8、Animation-fill-mode   规定动画在播放之前或者之后，其动画效果是否可见

​	None  不改变默认

​	Forwards  当动画完成后保持最后一个属性值

​	Backwards  在Animation –delay指定的一段时间之内，在动画显示之前，应用开始属性值。

​	Both  向前和向后填充模式都被应用。

简写语法：

Animation: name duration timing-function delay iteration -count direction



**关键帧语法**:



~~~
@keyframes 关键帧的名字 {
    0% {}
    30% {}
    50% {}
    100%{}
}

@keyframes 关键帧的名字 {
    from {}
    to{}
}
~~~






