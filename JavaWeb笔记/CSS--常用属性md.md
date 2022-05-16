## CSS起源

![img](https://img-blog.csdnimg.cn/20191212082037483.png)

> 分析:

> 有一个标题H1, 还有一些段落P标题是居中的, 段落也是居中的. 所以我们可以设置H标签和P标签的align属性等于center来实现,标题和段落都有颜色,都有字体,都有大小, 所以需要给文字包裹一个font标签, 然后通过font标签来设置颜色和字体以及大小

- 给标签设置属性的来修改样式缺点
  1. 需要记忆哪些标签有哪些属性, 如果该标签没有这个属性, 那么设置了也没有效果
  2. 当需求变更时我们需要修改大量的代码才能满足现有的需求
  3. HTML只有一个作用就是用来 `添加语义`
- 使用CSS来给标签添加样式的缺点
  1. 不用记忆哪些属性属于哪个标签
  2. 当需求变更时我们不需要修改大量的代码就可以满足需求
  3. 在前端开发中CSS只有一个作用, 就是用来修改样式
- CSS格式(内嵌样式)

```html
<head>
	<style type="text/css">
	        标签名称{
	            属性名称: 属性对应的值;
	            ...
	        }
	</style>
</head>
```

**注意点**

1. `style标签`必须写在head标签的开始标签和结束标签之间(也就是必须和title标签是兄弟关系)
2. style标签中的type属性其实可以不用写, 默认就是type="`text/css`"
3. 设置样式时必须按照固定的格式来设置. key: value, 其中:不能省略, 分号大多数情况下也不能省略

![img](https://img-blog.csdnimg.cn/20191212082338885.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTg5OTgw,size_16,color_FFFFFF,t_70)

## CSS书写格式

- 行内样式


> 可以直接将CSS代码写到开始标签当中.
>

```css
<div style = "color: red">我是盒子</div>
```

- 内嵌样式

> 可以在一对head标签中写上一堆style标签,然后在style中编写CSS代码.

```css
<head>
	<style type="text/css">
	        标签名称{
	            属性名称: 属性对应的值;
	            ...
	        }
	</style>
</head>
```

>
> 外链样式(开发中使用这种)

> 在开发中一般使用外链样式,可以单独的新建一个.css的文件,把CSS代码写到这个文件中,然后通过link标签把这个文件和.html文件关联起来.
>

```css
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <link rel="stylesheet" href="zy.css">
</head>
```

>
> 导入样式

> 单独新建一个.css的文件, 把CSS代码写到这个文件中,然后通过@import把这个文件和.html文件关联起来.
>

```css
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        @import "zy.css";
    </style>
</head>
```

- 
  外链样式和导入样式的区别

- 外链样式是通过link标签关联`html文件`, 而导入样式是通过@import关联html, 使用@import会产生兼容问题.
- 外链样式在显示界面的时候, 会先加载CSS样式, 再加载结构, 所以用户看到的界面一定是已经设置了样式. 导入样式在显示界面的时候, 会先加载结构,再加载样式,所以用户看到的界面的时候不一定设置了样式.

## CSS常见属性

### **文字属性**

- `font-style : 取值`

  - 作用: 规定文字样式
  - 取值

  > normal ： 正常的， 默认就是正常的
  > italic ： 倾斜的
- `font-weight : 取值`

  - 作用: 规定文字粗细

  - 取值

    > bold： 加粗
    > bolder： 比加粗还要粗
    > lighter： 细线， 默认就是细线

- font-size : 取值

  - 作用: 规定文字大小

  - 取值

    > 格式：font-size: 30px;
    > 单位：px（像素 pixel）
    > 注意点： 通过font-size设置大小一定要带单位， 也就是一定要写px

- font-family : 取值

  - 作用: 规定文字字体

  - 取值

  > 格式：font-family:“楷体”;
  >
  > 注意点：
  > 1.如果取值是中文， 需要用双引号或者单引号括起来
  > 2.设置的字体必须是用户电脑里面已经安装的字体

- 文字属性的缩写

  > 缩写格式:
  > font: style weight size family;
  > 例如:
  > font:italic bold 10px “楷体”;

- 注意点
  1. 在这种缩写格式中sytle、weight属性值可以省略
  2. 在这种缩写格式中style和weight的位置可以交换
  3. 在这种缩写格式中size、family属性值是不可以省略的
  4. size和family的位置是不能随便乱放,size在family前,都放在后

### **文体属性**

- `text-decoration : 取值`

  - 作用: 给文本添加装饰、

  - 取值

    > underline： 下划线
    > line-through： 删除线
    > overline： 上划线
    > none： 什么都没有, 最常见的用途就是用于 去掉超链接的下划线

- `text-align : 取值`

  - 作用: 设置文本水平对齐方式

  - 取值

    > left 左
    > right 右
    > center 中

- `text-indent : 取值`

- 作用: 设置文本缩进

- 取值

  > 2em, 其中em是单位, 一个em代表缩进一个文字的宽度

### 颜色属性

- `color : 取值`

  - 取值

    > 1、英文单词
    > 2、rgb
    > 3、rgba
    > 4、十六进制

### 盒子阴影和文字阴影

- 如何给盒子添加阴影
  `box-shadow: 水平偏移 垂直偏移 模糊度 阴影扩展 阴影颜色 内外阴影;`

- 注意点

  1. 盒子的阴影分为内外阴影,默认情况下就是外阴影.

  2. 添加阴影只需要三个参数即可.

     `box`-`shadow : 水平偏移 垂直偏移 模糊度;`

  3. 默认情况下阴影的颜色和盒子内容的颜色.

- 如何给文字添加阴影
  `text-shadow: 水平偏移 垂直偏移 模糊度 阴影颜色;`

```CSS
        .box1{
            width: 200px;
            height: 200px;
            background-color: red;
            margin: 100px auto;
            text-align: center;
            line-height: 200px;
            /*box-shadow: 10px 10px 10px 10px skyblue;*/
            /*box-shadow: 10px 10px 10px 10px skyblue inset;*/
            box-shadow: 10px 10px 10px;
            color: yellow;
        }
        .box2{
            width: 200px;
            height: 200px;
            margin: 0 auto;
            background-color: pink;
            text-align: center;
            line-height: 200px;
            font-size: 40px;
            /*text-shadow: 10px 10px 10px black;*/
            text-shadow: 10px 10px 10px;
            color: purple;
        }
```

### 背景相关属性

- 背景颜色属性

  - `background-color : 取值`

  - 取值

    > 1、英文单词
    > 2、rgb
    > 3、rgba
    > 4、十六进制

- 背景图片属性


- background-image: url();的属性, 专门用于设置背景图片.

- 注意点

  > 1. 图片的地址必须放在url()中, 图片的地址可以是本地的地址, 也可以是网络的地址
  > 2. 如果图片的大小没有标签的大小大, 那么会自动在水平和垂直方向平铺来填充
  > 3. 如果网页上出现了图片, 那么浏览器会再次发送请求获取图片

  ### 背景平铺属性

- `background-repeat属性, 就是用于控制背景图片的平铺方式.`

- 取值

  > 1、repeat 默认, 在水平和垂直都需要平铺
  > 2、no-repeat 在水平和垂直都不需要平铺
  > 3、repeat-x 只在水平方向平铺
  > 4、repeat-y 只在垂直方向平铺
- 应用场景

  > 可以通过背景图片的平铺来降低图片的大小, 提升网页的访问速度

### 背景定位属性

- `background-position:属性, 就是用于控制背景图片的位置`

- 格式
  `background-position: 水平方向 垂直方向;`

- 取值

  > 1、具体的方位名词
  > 水平方向: left center right
  > 垂直方向: top center bottom
  > 2、具体像素
  > 记住一定要写单位, 也就是一定要写px
  > 记住具体的像素是可以接收负数的

- 注意点

  > 同一个标签可以同时设置背景颜色和背景图片, 如果颜色和图片同时存在, 那么图片会覆盖颜色.

#### 背景属性缩写形式

- 格式
  `background: 背景颜色 背景图片 平铺方式 关联方式 定位方式;`

- 注意点
  `background属性中,任何属性都可以省略.`

- 什么是背景关联方式?

  > 认情况下背景图片会随着滚动条的滚动而滚动， 如果不想让背景图片随着滚动条的滚动而滚动， 那么我们就可以修改背景图片和滚动条的关联方式

- background-attachment的属性， 这个属性就是用于修改关联方式的.

- 格式

  `background-attachment：scroll;`

- 取值

  > 1、scroll 默认值， 会随着滚动条的滚动而滚动
  > 2、fixed 不会随着滚动条的滚动而滚动

- 背景图片和插入图片的区别

  > 1、背景图片仅仅是一个装饰,不会占用位置; 插入图片会占用位置.
  > 2、背景图片有定位属性, 所以可以很方便的控制图片的位置 ;插入图片没有定位属性, 所有控制图片的位置不太方便
  > 3、插入图片的语义比背景图片的语义要强, 所以在开发中如果你的图片想被搜索引擎收录, 那么推荐使用插入图片

### 边框属性

- 什么是边框?
  `边框就是环绕在标签宽度和高度周围的线条.`

- 格式(连写)	
  `border ：边框宽度 边框样式 边框颜色;`

- 注意点

  1. 连写格式中颜色属性可以省略,省略之后默认就是黑色.
  2. 连写格式中样式不能省略,省略后就看不到边框了.
  3. 连写格式中宽度可以省略,省略后还可以看到边框.

- 分别单独设置四条边的边框
  `border-top: 边框的宽度 边框的样式 边框的颜色;`
  `border-right: 边框的宽度 边框的样式 边框的颜色;`
  `border-bottom: 边框的宽度 边框的样式 边框的颜色;`
  `border-left: 边框的宽度 边框的样式 边框的颜色;`

- 边框样式中常见取值
  `border-style:取值`

  > solid 实线
  > double 双实线
  > dashed 虚线
  > dotted 圆点

- 分别先设置四条边的宽,样式,颜色

  > border-width: 上 右 下 左;
  > border-style: 上 右 下 左;
  > border-color: 上 右 下 左;

  - 注意点

    1. 这三个属性的取值是按照顺时针来赋值, 也就是按照上右下左来赋值
    2. 只设置上右下,左边的取值和右边的取值相同只设置上右, 左边的取值和右边相同,下边的取值和上边相同
    3. 只设置上, 则右下左边的取值和上边相同

  - 单独写(不建议)

    > border-left-width: 20px;
    > border-left-style: double;
    > border-left-color: pink;

### 内外边距属性

- 什么是内边距?
  `边框和内容之间的距离就是内边距.`

- 格式


> 非连写：
> padding-top: 值px;
> padding-right: 值px;
> padding-bottom: 值px;
> padding-left: 值px;
> 连写：
> padding: 上 右 下 左;

`注: 上右下左的取值省略规律同边框取值省略相同.`

- 注意点


1. 给标签设置内边距之后, 标签占有的宽度和高度会发生变化
2. 给标签设置内边距之后, 内边距也会有背景颜色

### 外边距属性

- 什么是外边距?
  `标签和标签之间的距离就是外边距.`

- 格式


> 非连写：
> margin-top: 值px;
> margin-right: 值px;
> margin-bottom: 值px;
> margin-left: 值px;
> 连写：
> margin: 上 右 下 左;

`注: 上右下左的取值省略规律同边框取值省略相同.`

- 注意点


1. 外边距的那一部分是没有背景颜色
2. 水平方向上, 外边距可以叠加
3. 在默认布局的垂直方向上,外边距不会叠加,会出现外边距合并, 谁的外边距大就听谁的

### div和span标签

- 什么是div?

  `作用: 一般用于配合css完成网页的基本布局.`

- 什么是span?

  `作用: 一般用于配合css修改网页中的一些局部信息.`

```css
<p>你<span>好</span>呀</p>
```

- div和span有什么区别?

  > 1.div会单独的占一行,而span不会单独占一行
  > 2.div是一个容器级的标签, 而span是一个文本级的标签

- 容器级的标签和文本级的标签的区别?

  `1.容器级的标签中可以嵌套其它所有的标签`
  `2.文本级的标签中只能嵌套文字/图片/超链接`

- 容器级的标签

  div h ul ol dl li dt dd …

- 文本级的标签
  span p buis strong em ins del …

### CSS元素的显示模式及模式转换

CSS元素的显示模式概述


> 在HTML中所有的标签分为两类, 分别是`容器级`和`文本级`
> 在CSS中所有的标签分为两类, 分别是`块级元素`和`行内元素`

```css
容器级的标签
    div h ul ol dl li dt dd ...
文本级的标签
    span p buis stong em ins del ...

块级元素
    p div h ul ol dl li dt dd
行内元素
    span buis strong em ins del
```

- 块级元素和行内元素的区别?

- 块级元素

  > 独占一行
  > 如果没有设置宽度, 那么默认和 父元素一样宽
  > 如果设置了宽高, 那么就按照设置的来显示

- 行内元素

- 不会独占一行

  > 如果没有设置宽度, 那么默认和内容一样宽
  > 行内元素是不可以设置宽度和高度的

- 块內级元素

  > 为了能够让元素既能够不独占一行, 又可以设置宽度和高度, 那么就出现了行内块级元素
  > img就是行内块级标签

### CSS元素的模式转换

- 如何转换CSS元素的显示模式?

  设置元素的display属性

  > display 取值
  > block： 块级
  > inline： 行内
  > inline-block： 行内块级

```css
<style>
    div{
        display: inline;
        background: red;
        width: 50px;
        height: 50px;
    }
    span{
        display: block;
        background: greenyellow;
        width: 50px;
        height: 50px;
    }
    .cc{
        background: greenyellow;
        width: 50px;
        height: 50px;
        display: inline-block;
    }
</style>
```
```css
<div>我是div</div>
<div>我是div</div>

<span>我是span</span>
<span>我是span</span>

<p class="cc">我是段落</p>
<b class="cc">我是加粗</b>
```

### 盒子模型

- 什么是CSS盒子模型?
  `CSS盒子模型是一个形象比喻,HTML中所有标签都是一个盒子.`

  在HTML中所有的标签都可以设置:`宽度/高度 边框 内边距 外边距.`

- 盒子模型的宽度和高度

  - 内容的宽度和高度

  > 通过width/height属性设置的宽度和高度
  - 元素的宽度和	高度

    > 宽度 = 左边框 + 左内边距 + width + 右内边距 + 右边框
    > 高度 同理可证

  - 元素空间的宽度和高度

  > 宽度 = 左外边距 + 左边框 + 左内边距 + width + 右内边距 + 右边框 + 右外边距
  > 高度 同理可证

- 盒子box-sizing属性

  1. CSS3中新增一个box-sizing属性, 这个属性可以保证我们给盒子新增padding和border之后, 盒子元素的宽度和高度不变.
  2. 原理: 增加padding和border之后要想保证盒子元素的宽高不变, 那么就必须减去一部分内容的宽度和高度.

- box-sizing:取值

  > content-box 元素的宽高 = 边框 + 内边距 +内容宽高
  > border-box 元素的宽高 = 设置width/height的宽高

- 注意点

  1. 如果两个盒子是嵌套关系,那么设置里面的盒子顶部外边距,外面的盒子也会被顶下来

  2. 若外面的盒子不想被定下来,可以给外面的盒子添加一个边框属性

  3. 开发中, 如果需要控制嵌套关系盒子直接的距离,首先考虑使用padding,再考虑margin

     `padding`本质上是用于控制父子关系之间的间隙

     `margin`本质上是用于控制兄弟关系之间的间隙

  4. 在嵌套关系的盒子中, 我们可以利用 `margin: 0 auto` 的方式让里面的盒子相对于外边盒子水平居中

  5. margin:0 auto; 只对水平方向有效, 对垂直方向无效.

- text-align:center;和margin:0 auto;区别

  - text-align:center 让盒子中存储的文字/图片水平居中
  - margin:0 auto 让盒子本身水平居中

- 清空默认边距

  ```css
  body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td{
              margin:0;padding:0
  }
  ```

  `注意: 使用 * (通配符选择器)会遍历当前界面上所有标签,性能差,不建议使用.`

- 行高属性

  - 什么是行高?
    `在CSS中所有的行都有自己的行高.`

- 注意点

  1 行高和盒子高不同
  2 行高指的是每行内容的高度; 盒子高指的是元素的高度.
  3 文字在行高中默认是垂直居中的
  4 要想一行文字在盒子中垂直居中, 那么只需要设置这行文字的"行高等于盒子的高"即可
  5 想让盒子中多行文字居中,需要设置 `padding` 让文字居中,然后设置box-sizing属性来保证盒子元素的宽高不变.