# 一、HTML

## 1. 表格

合并行：rowspan="合并数量"

合并列：colspan="合并数量"

清除空白单元格之间的空白：cellspacing=”0“

内容边距类似padding：cellpadding=“需要的距离”



------



## 2. 新增加语义化标签

| 标签    | 作用         |
| ------- | ------------ |
| header  | 头部标签     |
| nav     | 导航标签     |
| article | 内容标签     |
| section | 定义文档标签 |
| aside   | 侧边栏标签   |
| footer  | 尾部标签     |

注：

1.移动端常用

2.需要转化为块级元素

------



## 3. 新增input 表单属性

| 属性         | 值        | 说明                                                         |
| ------------ | --------- | ------------------------------------------------------------ |
| required     | required  | 表单拥有该属性表示其他内容不能为空，必填                     |
| placeholder  | 提示文本  | 表单的提示信息，存在默认值将不显示                           |
| autofocus    | autofocus | 自动聚焦属性，页面加载完成自动聚焦到指定表单                 |
| autocomplete | off/on    | 当用户在字段开始键入时，游览器基于之前键入过的值，应该显示在字段中填写的选项。                              默认已经打开，如autocomplete=“on”,关闭autocomplete=“off” 需要放在表单内，同时加上name属性，同时提交成功 |
| multiple     | multiple  | 可以选择多文件提交                                           |

------



## 4. 视频音频标签

## 4.1 视频标签

语法：

```html
<video src= "文件地址" controls="controls"></video>
```

#### 4.1.1 游览器支持

```html
<video width="320" height="240" controls="controls">
	<source src="movie.mp4" type="video/mp4">
	<source src="movie.ogg" type="video/ogg">
	您的游览器不支持 video 标签
</video>
```

#### 4.1.2视频标签常见属性

| 属性     | 值                                      | 描述                                                      |
| -------- | --------------------------------------- | --------------------------------------------------------- |
| autoplay | autoplay                                | 视频就绪自动播放（谷歌游览器添加muted来解决自动播放问题） |
| controls | controls                                | 显示播放控件（播放展厅按钮等）                            |
| loop     | loop                                    | 播放完是否继续播放，循环播放                              |
| preload  | auto(预先加载视频)   none（不预先加载） | 如果有了autoplay 就忽略该属性                             |
| poster   | imgurl                                  | 加载等待画面的图片                                        |
| mutef    | muted                                   | 静音播放                                                  |
|          |                                         |                                                           |



------

## 5. 音频标签

语法

```
//<audio src= "文件地址"  controls="controls"></audio>
```

```
//<audio  controls="controls">
	<source src="horse.ogg" type="audio/mp4">
	<source src="movie.ogg" type="video/ogg">
	您的游览器不支持 <audio> 标签
</audio>
```



------



# 二. CSS

## 1. css缺点

css是一门非程序式语言，没有变量，函数，scope（作用域）等概念

- css需要书写大量看似没有逻辑的代码，css冗余度是比较高的
- 不方便维护及拓展，不利于复用
- css没有很好的计算能力
- 非前端开发工程师来讲，往往会因为缺少css编写经验而很难写出组织良好易与维护的css代码项目

## 2. font字体属性

| 文本属性                   | 描述                               |
| -------------------------- | ---------------------------------- |
| font-family:'字体名称'     | 字体（列如楷体等）                 |
| font-size:字体大小（像素） | 字体大小                           |
| font-weight: 属性值        | 字体加粗                           |
| font-style:字体样式        | 字体样式（字体，大小，粗细，倾斜） |

------



## 3. text文本属性

| 文本属性                                                     | 描述                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| text-align:center \| left \|right;                           | 文本对齐、水平居中：                                 |
| text-decoration:none \|  underline\|line-through \|overline  | 文本装饰:                                            |
| text-indent:值（像素）                                       | 文本缩进（em：当前字体大小的字符）                   |
| line-height:数值                                             | 行间距、垂直居中（当行高等于自身高度时内容垂直居中） |
| text-shadow                                                  | 文字阴影                                             |
| 文字阴影：h-shadow水平（必填） v-shadow垂直（必填）blur模糊 spread （阴影） color（颜色） |                                                      |

------

### 3.1 基线对齐（图片下方有缝隙解决办法）

| vertical-align值 | 描述                                   |
| ---------------- | -------------------------------------- |
| baseline         | 默认，元素放置在父元素的基线上。       |
| top              | 把元素的顶端与行中最高元素的顶端对齐   |
| middle           | 把元素放置在父元素的中部               |
| bottom           | 把元素的顶端与行中最低的元素的顶端对齐 |

**图片下方缝隙：**

1.运用上方基线middle中线对齐

2.转化为块级元素（dispaly:block）



------



### 3.2 文本溢出省略号显示

**单行溢出：**

```css
/*1.先强制一行内显示文本*/
white-space: nowrap;(默认 normal 自动换行)
/*2。超出的部分隐藏*/
overflow:hidden;
/*3.文字用省略号代替超出的部分*/
text-overflow: ellipsis;
```



**多行溢出**：

```css
overflow:hidden;
text-overflow: ellipsis;
/*弹性伸缩盒子模型显示*/
display: -webkit-box;
/*限制在一个块级元素显示的文本的行数*/
-webkit-line-clamp:2;
/*设置或检索伸缩盒对象的子元素的排列方式*/
-webkit-box-orient : vertical;
```

------



## 4. CSS伪连接

| 属性           | 描述                 |
| :------------- | -------------------- |
| a:link         | 未被选中时           |
| a:visited      | 已经访问点击过的链接 |
| a:hover        | 鼠标悬停时           |
| a:active       | 点击链接时           |
| Cursor:pointer | 让鼠标变成小手       |



------



## 5. css行内块



| 元素       | 描述                                  |
| ---------- | ------------------------------------- |
| 块级元素   | 独占一行，可以设置长宽                |
| 行内元素   | 一行多个，不能直接设置长宽            |
| 行内块元素 | 块+行的特点，一行多个可以直接设置长宽 |

| display属性值          | 描述                   |
| ---------------------- | ---------------------- |
| block（块）            | 将元素转化为块级元素   |
| inline（行内）         | 将元素转化为行内元素   |
| inline-block（行内块） | 将元素转化为行内块元素 |



------



## 6. css背景 颜色 图片 渐变

| background属性值                       | 描述                              |
| -------------------------------------- | --------------------------------- |
| background-color                       | 背景颜色默认为transparent（透明） |
| background-image                       | 背景图片 必填：url（图片路径）    |
| background-repeat                      | 背景是否平铺和平铺方向            |
| background-attachment                  | 背景图片固定或移动 （默认固定）   |
| background-position                    | 背景位置（用方位名词或者数值）    |
| background-size                        | 背景图片大小                      |
| background: -webkit-linear-gradient(); | 背景渐变必须添加游览器私有前缀    |

背景渐变起始方向可以是：方位名词 或者 度数，如果省略默认是top

```css
background: -webkit-linear-gradient(top left ,red ,blue);
//从左上角开始到右下角为红蓝色
```

background-size属性

| 属性                       | 描述                                                         |
| -------------------------- | ------------------------------------------------------------ |
| background-size:50px 50px; | 背景图片宽高为50px                                           |
| background-size:50px；     | 默认为是宽度，高度省略，自动等比例缩放                       |
| background-size:50%；      | 相对于父盒子的50%                                            |
| background-size:cover；    | 完全覆盖盒子，可能有部分图片显示不全                         |
| background-size:contain；  | 高度和宽度等比例拉伸，直到宽或高到边上就不在拉伸，可能存在留白的情况 |



------



## 7. css盒子  合并边框

| border属性值               | 描述                                             |
| -------------------------- | ------------------------------------------------ |
| border-style               | 边框样式solid实线\|dashed虚线\|dotted点线        |
| border-color               | 边框颜色                                         |
| border-left                | 边框的边还有right、bottom、top                   |
| border: 1px solid red      | 复合型写法：宽度   样式  颜色                    |
| border-radius:length       | 圆角矩形，当盒子长宽一样时，值为其一半则为正方形 |
| border-top-right-radius    | 右上角变圆角，其它角同理                         |
| outline-style              | 外边线样式                                       |
| border-collapse: collapse; | 合并边框**（属于table标签样式仅table使用）**     |

网页在放大缩小时，边框会变大可能会导致内容掉下来

 /* 方案1：预留缩放到极限时，多出来的边框距离 */

  /* 方案2：不用边框采用阴影 */

------



### 7.1 css边距bug

- **当上下两个盒子都设置了外边距的时候**

**情况：**

上个设置了margin-bottom，下盒子设置了margin-top

会出现上下盒子间的距离只会取他们的最大那个作为间距

**解决办法**：

只需给一个盒子设置即可要么上盒子设置margin-bottom，要么下盒子设置margin-top

- **当盒子处于嵌套或者子代关系时**

  **情况**：

  里面盒子设置margin-top时不会与外盒子分开，反而会带着外面的盒子一起变远，

  **解决办法：**

  1. 给父级（外盒子）设置一个边框
  2. 给父级（外盒子）设置一个内边距
  3. 添加overflow:hidden;



------



### 7.2  css盒子阴影

| box-shadow属性 | 描述                             |
| -------------- | -------------------------------- |
| h-shadow       | 水平（必填）                     |
| v-shadow       | 垂直（必填）                     |
| blur           | 模糊                             |
| spread         | 阴影                             |
| color          | 颜色                             |
| inset          | （将外部（outset）改为内部阴影） |

注：outset为默认外部不可以写但是可以写inset改为内部



------



### 7.3 盒子浮动

| 属性          | 描述     |
| ------------- | -------- |
| float: left;  | 往左浮动 |
| float: right; | 往右浮动 |
|               |          |

1.浮动元素会压住他下面标准流盒子，但是不会压住标准流里面的文字（图片）

2.浮动会这样是因为浮动最初产生是为了文字环绕，文字会围绕浮动元素



------



#### 7.3.1 清除浮动

| 属性         | 描述                           |
| ------------ | ------------------------------ |
| clear:left;  | 清除左浮动带来的影响           |
| clear:right; | 清除右浮动带来的影响           |
| clear:both;  | 清除两边浮动带来的影响（常用） |

此法时采用的：闭合浮动

额外的标签方法：

1. 额外的标签法也称为隔墙法，是w3c推荐的方法：列如：在浮动的最后一个盒子后加上一个标签（必须是块级元素标签）创建调用clear:both;（优点：通俗易懂，书写方便）（缺点：添加许多无意义的标签，结构化较差）**不推荐使用**

2. 父级添加overflow属性：（优点：代码简洁）（缺点：无法显示溢出的部分）

3. 父级添加after伪元素! 

   源码书写：

   ```css
   .clearfix::after {
         content: "";
         display: block;
         height: 0;
         clear: both;
         visibility: hidden;
       }
       .clearfix {
        /* IE6、7专有 */
         *zoom:1;
       }
   
   ```

   类似额外标签法，相当于在最后一个盒子后按添加了一个盒子，此法不需要写标签（优点：没有增加标签，结构更简单）（缺点：需要照顾低版本的游览器）

4. 父级添加双伪元素(优点：代码更简洁)（缺点：照顾低版本游览器）

   ```css
    .clearfix::before , .clearfix::after {
               content: "";
               display: table;
           }
           .clearfix:after {
               clear: both;
           }
           .clearfix {
               *zoom: 1;
           }
   ```

   

------

### 7.4 css3盒子模型

```css
box-sizing:content-box;//传统盒模型
传统盒子模型 = width + border + padding
//给了盒子边框和内边距会导致盒子撑大
box-sizing:border-box;
css3盒子模型 //宽度是多少不管bordr和padding是多少都不会改变
```



## 8. 定位

### 8.1 静态定位

position:static 

------



### 8.2 相对定位

*position:relative 

```css
 {
position:relative
	left:100px;
    right:100px;
}
```

特点：1.它是相对于自己原来的位置来移动的（移动个位置的时候参照点是自己原来的位置）

2.原来在标准流的位置继续占有，后面的盒子任然以标准流的方式对待他（不脱标，继续保留原来的位置）



------



### 8.3 绝对定位

*position:absolute 绝对定位

特点1.如果**没有祖先元素**或者**祖先元素没有定位**，则以游览器为准定位（Document）

2.如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动位置

3.绝对定位**不再占用原先位置**（脱标）

口诀：子绝父相

子元素里面加上了绝对定位：position:absolute时

在父元素的样式中也要加上相对定位position:relative  

列子：

```css
.father{
	position:relative  
}
.son {
	position:absolute
	top:0
	left0
}
```



------



### 8.4 固定定位

position:fixed;

特点：

1.以游览器的可视窗口为参照点移动元素

- 根父元素没有任何关系

- 不随滚动条滚动

  2.固定定位不占有原先的位置

固定定位也是脱标的，其实固定定位也可以看做是一种特殊的绝对定位



------



### 8.5 粘性定位

position:Sticky 粘性定位

特点：

1.以游览器的可视化窗口为参照移动元素（固定定位特点）

2.粘性定位占有原先的位置（相对定位特点）

3.必须添加top、left、right、bottom其中一个才有效

跟页面滚动搭配使用。兼容性较差，IE不支持。

------



### 8.6 定为总结



| 定位模式         | 是否脱标       | 移动位置         | 是否常用   |
| ---------------- | -------------- | ---------------- | ---------- |
| static静态定位   | 否             | 不能使用边偏移   | 很少       |
| relative相对定位 | 否(占有位置)   | 相对于自身位置移 | 常用       |
| absolute绝对定位 | 是(不占有位置) | 带有定位的父级   | 常用       |
| fixed固定定位    | 是(不占有位置) | 浏览器可视区     | 常用       |
| sticky粘性定位   | 否(占有位置)   | 浏览器可视区     | 当前阶段少 |

------



### 8.7 定位的叠放次序

z-index 控制盒子的前后次序

```css
选择器{
z-index:1;
}
```

- 数值可以时正整数，负数或者0，默认是auto，数值越大，盒子越靠上
- 如果值是相同的，则按照顺序，后来居上
- 数字后面不能加单位
- 只有定位的盒子才有z-index属性

------



### 8.8 定位拓展

定位的特殊性

绝对定位和固定定位也和浮动类似

1.行内元素添加绝对或者固定定位，可以直接设置高度和宽度

2.块级元素不给设置宽度和高度，大小是内容的默认大小

3.脱标的盒子不会触发外边距塌陷，浮动元素和绝对定位（固定定位）元素都不会触发外边距合并的问题

4.绝对定位（固定定位）会完全压住盒子

浮动元素不同，只会压住他下面标准流盒子，但是不会压住标准流里面的文字（图片）

但是绝对定位（固定定位）会压住下面标准流所有的内容

------



##  8.9 *隐藏显示元素

**display**:block; 显示

**display:**none；隐藏

特点：

隐藏之后**不占有原来的位置**



**visibility:**visible; 元素可视

**visibility:**hidden 元素隐藏

特点：

visibility 隐藏元素后，**继续占有原来的位置**

------



### 8.10溢出隐藏



```css
 选择器 {
 	//不剪切内容也不添加滚动条
     overflow: visible;
     //不显示超过对象尺寸的内容，超标出部分隐藏掉
 	overflow:hidden;
 	//scroll 溢出部分显示滚动条，不溢出也显示滚动条
     overflow:scroll;
     //溢出时才显示滚动条，不溢出不显示滚动条
     overflow:auto
}
```

一般情况下，我们都不想让溢出内容显示出来，因为溢出的部分会影响布局

但是如果有定位的盒子，请慎用overflow:hidden; 因为他会隐藏多余的部分





------



## 9.0 新属性选择器

| 选择符           | 简介                                  |
| ---------------- | ------------------------------------- |
| E[att]           | 选择具有att属性的E元素                |
| **E[att="val"]** | 选择具有att属性且属性值等于val的E元素 |
| E[att^="val"]    | 匹配具有att属性且值以val开头的E元素   |
| E[att$="val"]    | 匹配具有att属性且值以val结尾的E元素   |
| E[att*="val"]    | 匹配具有att属性值中含有val的E元素     |

列如：



```css
E[att]:
<input type="text" value=""> //input[value] 选中input代码中带有value这个属性的元素
<input type="text" value="">
///////////////////////////////////

E[att="val"]：
<input type="text" value="">
<input type="password" value="">//input[type="text"]  选中input中带有type=“text

E[att^="val"]：
<div class="demo1">
<div class="demo2">
<div class="demo3">
//div[class^="demo"]  选中div中class=demo前缀的

E[att$="val"] ：
同E[att^="val"]相反 选出的结尾相同的属性[class$="demo"]


E[att*="val"]:
div[class*=”top“ ]选中所有含有top的不分前后
```



------



### 9.1 结构伪类选择器

| 选择符           | 简介                       |
| ---------------- | -------------------------- |
| E:first-child    | 匹配父元素中国的第一个元素 |
| E:last-child     | 匹配父元素中最后一个元素   |
| E:btht-child(n)  | 匹配父元素中的第n个元素    |
| E:first-of-type  | 指定类型E的第一个          |
| E:last-of-type   | 指定类型E的第最后一个      |
| E:nth-of-type(n) | 指定类型E的第n个           |

E:btht-child(n) 拓展用法：

1.n可以数字、关键字和公式

2.n如果是数字，就是选择第n个元素，里面数字从1开始...

3.n可以是关键字：even偶数（和2n一样选中所有偶数）、odd奇数（和2n+1一样选中所有的奇数）

4.2n（偶数）、2n+1奇数、5n（5的倍数）、n+5（从第五个开始）、-n+5（前五个包含第五个）



------



### 9.2 伪元素选择器after

| 选择符   | 简介                     |
| -------- | ------------------------ |
| ::before | 在元素内部的前面插入内容 |
| ::after  | 在元素内部的后面插入内容 |

注意：

- before和after创建一个元素，但是属于行内元素
- 新创建的这个元素在文档中是找不到的，所以我们称为伪元素
- 语法：element::before{}
- before和after必须有content属性
- before在父元素内容的前面创建元素，after在父元素内容的后面插入元素
- 伪元素选择器和标签选择器一样，权重为1



------



## 10.0 过度动画

transition:要过度的属性  花费时间  运动曲线  何时开始

一般都是配合hover使用，**谁做过度给谁加**

1. 属性：想要变化的css属性，宽度高度 背景颜色 内外边距都可以。如果想要所有属性都变化过程，写一个all就可以。
2. 花费时间：单位是 秒（必须写单位） 列：0.5s
3. 运动曲线：默认是ease（可以省略）
4. 何时开始运动：单位是秒（必须写单位） 可以设置延时触发时间 默认是0s（可以省略）



------



## 11.0  2D转换  transform 

类似 定位 、 外边距 使盒子位移

语法：

```css
transform：translate(x,y);//或者分开写
transform：translateX(n);
transform：translateY(n);
```

盒子垂直居中：

```css
position:absolute;
top:50%;
left:50%;
transform: translate(-50%, -50%);//盒子走自己宽高一半的距离
transform: scale(放大倍数)；
```

2.特点

- 定义2d转换中的移动。沿着X和Y轴移动元素
- translate最大的优点：不会影响到其他元素的位置
- translate中的百分比单位是相对于自身元素的translate:(50%,50%);
- 对行内标签没有效果



------



### 11.1  2D旋转



语法：

```css
transform:rotate(旋转度数)
```

特点：

- rotate里面跟度数，单位是deg比如：rotate（45deg）
- 角度为正时，顺时针，负时，为逆时针
- 默认旋转的中心点是元素中心点

------



#### 11.1.1 2D旋转中心点

语法：



```css
transform-origin: x y;
```

重点

- 注意后面的参数x和y用空格隔开
- x y 默认转换的中心点事元素的中心点(50% 50%)
- 还可以给 x y 设置 像素 或者 方位名词 ( top bottom left right center默认)

------



###  11.1.2  2D转换 缩放

```
transform-origin:scale(放大倍数);
//不跟单位，1就是放大一倍
transform-origin:scale(x，y);
//x宽 ， y、高
transform-origin:scale(2，4)
//宽为原来的2倍，高为原来的4倍
transform-origin:scale(0.2，0.4)
//宽缩放为原来的0.2，高缩放0.4
```

------



### 11.1.3  2D转换综合写法

注意：

1. 同时使用多个转换，其格式为：

```css
transform:translate() rotate() scale()...等
```

2.其顺序会影响转换的效果。（先旋转会改变坐标轴方向）

3.当我们同时有位移和其他属性的时候，要将位移放在最前面

------



## 12.0 动画

用keyframes定义动画（类似定义类选择器）

```css
@keyframes 动画名称 {
//动画开始
0% {
	width:100px
}
//动画结束
100% {
	width:100%
}
}
//用百分比或者from（0%）和to（100%）
```

 

------



### 12.1 动画常用属性

|           属性            | 描述                                                         |
| :-----------------------: | ------------------------------------------------------------ |
|        @keyframes         | 规定动画                                                     |
|         animation         | 所有动画属性的简写属性，出了animation-play-stale属性         |
|      animation-name       | 规定@keyframes动画名称（必须的）                             |
|    animation-duration     | 规定动画完成一个周期所花费的秒或毫秒,(默认是0)（必须的）     |
| animation-timing-function | 规定动画速度曲线，默认是“ease”                               |
|      animation-delay      | 规定动画何时开始，默认值是0                                  |
| animation-iteration-count | 规定动画被播放次数，默认是1，还有infinite（循环）            |
|    animation-direction    | 规定动画是否在一下一次周期逆向播放，默认是‘normal’，alternate逆播放 |
|   animation-play-state    | 规定动画是否正在运行或暂停，默认是‘running’，还有‘paused’（暂停） 一般配合hover使用 |
|         animation         | 规定动画结束后的状态，保持forwards回到起始backwards          |

 

------



### 12.2 动画简写

animation:动画名称  持续时间  运动曲线  何时开始  播放次数  是否反方向  动画起始或者结束状态

调用多个动画时用逗号隔开

------



### 12.3 动画曲线

animation-timing-function：规定动画的曲线速度。默认是‘ease’

| 值          | 描述                                           |
| ----------- | ---------------------------------------------- |
| linear      | 动画从头到尾的速度是相同的，匀速               |
| ease        | 默认。动画以低速开始吗，然后加快，在结束前变慢 |
| ease-in     | 动画以低速开始                                 |
| ease-out    | 动画以低速结束                                 |
| ease-in-out | 动画以低速开始和结束                           |
| steps()     | 指定了时间函数中的间隔数量（步长）f            |
| steps(4)    | 分4步来完成动画                                |

------



## 13.0 3D转换

语法

```
transform:translate3d(x,y,z)
```

透视：

```
perspective
```

透视值越小，图像越大



写在被观察元素的父盒子上面

3D呈现

```
transform-style:flat (默认关闭3d立体空间)
transform-style:preserve-3d; (子元素开启立体空间)
```

- 控制子元素是否开启3D立体环境
- transform-style:flat子元素不开启3D立体空间 默认的
- transform-style:preserve-3D;子元素开启立体空间
- 代码写给父级，但是影响的是子盒子
- 这个属性很重要，后面必用