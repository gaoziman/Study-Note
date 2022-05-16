# 一、初始CSS

## CSS简介

------

CSS是一种描述HTML文档式的语言。

**CSS 描述应该如何显示 HTML 元素。**

本次教程将从零开始带您进入CSS的世界！

# 二、走进CSS

------

## CSS简介

------

### 什么是 CSS？

- *CSS* 指的是层叠样式表***(Cascading Style Sheets)**
- CSS 描述了**如何在屏幕、纸张或其他媒体上显示 HTML 元素**
- CSS *节省了大量工作*。它可以同时控制多张网页的布局
- 外部样式表存储在 *CSS 文件*中

***：**也称级联样式表。

------

#### CSS 演示

 - 一张 HTML 页面 - 多个样式！

下面是一张提供了四个不同样式表的 HTML 页面。请单击下面的样式表链接，来查看不同的样式：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-11_22-44-27.png" style="zoom:80%;" />

------

### 为何使用 CSS？

CSS用于定义网页的样式，包括针对不同设备和屏幕尺寸的设计和布局。

#### CSS实例

```css
body {
  background-color: lightblue;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 20px;
}
```

------

### CSS 解决了一个大问题

HTML 从未打算包含用于格式化网页的标签！

创建 HTML 的目的是*描述网页*的内容，例如：

```css
<h1>这是一个标题。</h1>

<p>这是一个段落。</p>
```

将 <font> 之类的标签和 color 属性添加到 HTML 3.2 规范后，Web 开发人员的噩梦开始了。大型网站的开发将字体和颜色信息添加到每个页面中，这演变为一个漫长而昂贵的过程。

为了解决这个问题，万维网联盟（W3C）创建了 CSS。

CSS 从 HTML 页面中删除了样式格式！

------

### CSS 节省了大量工作！

样式定义通常保存在外部 .css 文件中。

通过使用外部样式表文件，您只需更改一个文件即可更改整个网站的外观！

------

## CSS语法

### 悉知CSS 语法

CSS 规则集（rule-set）由选择器和声明块组成：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-21-27.png)

选择器指向您需要设置样式的 HTML 元素。

声明块包含一条或多条用分号分隔的声明。

每条声明都包含一个 CSS 属性名称和一个值，以冒号分隔。

多条 CSS 声明用分号分隔，声明块用花括号括起来。

### 实例

在此例中，所有 <p> 元素都将居中对齐，并带有红色文本颜色：

```css
p {
  color: red;
  text-align: center;
}

```



------

### 例子解释

- p 是 CSS 中的*选择器*（它指向要设置样式的 HTML 元素：<p>）。
- color 是属性，red 是属性值
- text-align 是属性，center 是属性值

在下一章中，您将学到更多关于 CSS 选择器和 CSS 属性的知识。

------

## CSS选择器

------



### 悉知CSS选择器

CSS 选择器用于“查找”（或选取）要设置样式的 HTML 元素。

我们可以将 CSS 选择器分为五类：

- 简单选择器（根据名称、id、类来选取元素）
- **组合器选择器**（根据它们之间的特定关系来选取元素）
- **伪类选择器**（根据特定状态选取元素）
- **伪元素选择器**（选取元素的一部分并设置其样式）
- **属性选择器**（根据属性或属性值来选取元素）

下面了解最基本的选择器

------

### CSS元素选择器

元素选择器会根据元素的名称来选择HTML元素。

#### 实例

在这里，页面上的所有 <p> 元素都将居中对齐，并带有红色文本颜色：

```css
p {
  text-align: center;
  color: red;
}
```

------

### CSS id 选择器

id 选择器使用 HTML 元素的 id 属性来选择特定元素。

元素的 id 在页面中是唯一的，因此 id 选择器用于选择一个唯一的元素！

要选择具有特定 id 的元素，请写一个井号（＃），后跟该元素的 id。

> 注意：id选择器在一个页面是唯一的，只能被选择一次。

#### 实例

这条 CSS 规则将应用于 id="para1" 的 HTML 元素：

```css
#para1 {
  text-align: center;
  color: red;
}
```

------

### CSS 类选择器

> 类选择器选择有特定 class 属性的 HTML 元素。
>
> 如需选择拥有特定 class 的元素，请写一个句点（.）字符，后面跟类名。

#### 实例

在此例中，所有带有 class="center" 的 HTML 元素将为红色且居中对齐：

```css
.center {
  text-align: center;
  color: red;
}
```

HTML元素也可以引用多个类

#### 实例

在这个例子中，<p> 元素将根据 class="center" 和 class="large" 进行样式设置：

```css
<p class="center large">这个段落引用两个类。</p>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-37-46.png" style="zoom:150%;" />

> **注意：**类名不能以数字开头！

------

### CSS 通用选择器

通用选择器（*）选择页面上的所有的 HTML 元素。

#### 实例

下面的 CSS 规则会影响页面上的每个 HTML 元素：

```css
* {
  text-align: center;
  color: blue;
}
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-39-26.png" style="zoom:150%;" />

------

### CSS 分组选择器

分组选择器选取所有具有相同样式定义的 HTML 元素。

请看下面的 CSS 代码（h1、h2 和 p 元素具有相同的样式定义）：

```css
     h1 {
      text-align: center;
      color: red;
    }

    h2 {
      text-align: center;
      color: red;
    }

    p {
      text-align: center;
      color: red;
    }
```

> 最好对选择器进行分组，以最大程度地缩减代码。
>
> 如需对选择器进行分组，请用逗号来分隔每个选择器。

#### 实例

在这个例子中，我们对上述代码中的选择器进行分组：

```css
 h1, h2, p {
  text-align: center;
  color: red;
 }
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-42-15.png" style="zoom:150%;" />

------

### 所有简单的CSS选择器

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-43-20.png" style="zoom:150%;" />

------

## CSS的使用

### 如何添加CSS

------

> 当浏览器读到样式表时，它会根据样式表中的信息来格式HTML文档。

------

### 三种使用 CSS 的方法

有三种插入样式表的方法：

- 外部 CSS
- 内部 CSS
- 行内 CSS

------

### 外部 CSS

通过使用外部样式表，您只需修改一个文件即可改变整个网站的外观！

每张 HTML 页面必须在 head 部分的 <link> 元素内包含对外部样式表文件的引用。

#### 实例

外部样式在 HTML 页面 <head> 部分内的 <link> 元素中进行定义：

```css
    <!DOCTYPE html>
    <html>
    <head>
    <link rel="stylesheet" type="text/css" href="mystyle.css">
    </head>
    <body>

    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>

    </body>
    </html>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-48-31.png" style="zoom:150%;" />

外部样式表可以在任何文本编辑器中编写，并且必须以 .css 扩展名保存。

外部 .css 文件不应包含任何 HTML 标签。

"mystyle.css" 是这样的：

 "mystyle.css"

```css
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

> **注意：**请勿在属性值和单位之间添加空格（例如 **margin-left: 20 px;**）。正确的写法是：**margin-left: 20px;**

------

### 内部 CSS

如果一张 HTML 页面拥有唯一的样式，那么可以使用内部样式表。

内部样式是在 head 部分的 <style> 元素中进行定义。

#### 实例

内部样式在 HTML 页面的 <head> 部分内的 <style> 元素中进行定义：

```css
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
} 
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-52-03.png" style="zoom:200%;" />

------

### 行内 CSS

行内样式（也称内联样式）可用于为单个元素应用唯一的样式。

如需使用行内样式，请将 style 属性添加到相关元素。style 属性可包含任何 CSS 属性。

#### 实例

行内样式在相关元素的 "style" 属性中定义：

```css
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-53-52.png" style="zoom:200%;" />

> **提示：**行内样式失去了样式表的许多优点（通过将内容与呈现混合在一起）。请谨慎使用此方法。

------

### 多个样式表

如果在不同样式表中为同一选择器（元素）定义了一些属性，则将使用最后读取的样式表中的值。

假设某个*外部样式表*为 <h1> 元素设定的如下样式：

```css
h1 {
  color: navy;
}
```

然后，假设某个*内部样式表*也为 <h1> 元素设置了如下样式：

```css
h1 {
  color: orange;    
}
```

#### 实例

如果内部样式是在链接到外部样式表*之后*定义的，则 <h1> 元素将是橙色：

```css
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
<style>
h1 {
  color: orange;
}
</style>
</head>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_10-56-10.png" style="zoom:200%;" />

#### 实例

不过，如果在链接到外部样式表*之前*定义了内部样式，则 <h1> 元素将是深蓝色：

```css
<head>
<style>
h1 {
  color: orange;
}
</style>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

------

### 层叠顺序

当为某个 HTML 元素指定了多个样式时，会使用哪种样式呢？

页面中的所有样式将按照以下规则“层叠”为新的“虚拟”样式表，其中第一优先级最高：

1. 行内样式（在 HTML 元素中）
2. 外部和内部样式表（在 head 部分）
3. 浏览器默认样式

> 因此，行内样式具有最高优先级，并且将覆盖外部和内部样式以及浏览器默认样式。

------

## CSS 注释

------

### 悉知CSS 注释

注释用于解释代码，以后在您编辑源代码时可能会有所帮助。

浏览器会忽略注释。

位于 <style> 元素内的 CSS 注释，以 /* 开始，以 */ 结束：

#### 实例1

```css
/* 这是一条单行注释 */
p {
  color: red;
}
```

您可以在代码中的任何位置添加注释：

#### 实例2

```css
p {
  color: red;  /* 把文本设置为红色 */
}
```

注释能横跨多行：

#### 实例3

```css
/* 这是
一条多行的
注释 */ 

p {
  color: red;
}
```

------

### HTML 和 CSS 注释

从 HTML 中，您学习到可以使用 <!--...--> 语法在 HTML 源代码中添加注释。

在下面的例子中，我们结合使用了 HTML 和 CSS 注释：

#### 实例

```css
<!DOCTYPE html>
<html>
<head>
<style>
p {
  color: red; /* 将文字颜色设置为红色 */
} 
</style>
</head>
<body>

<h2>My Heading</h2>

<!-- 这些段落将是红色的 -->
<p>Hello World!</p>
<p>这段文本由 CSS 设置样式。</p>
<p>CSS 注释不会在输出中显示。</p>

</body>
</html>
```

------

## CSS文本

------

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-26-38.png" style="zoom:80%;" />

------

### 文本颜色

color 属性用于设置文本的颜色。颜色由以下值指定：

- 颜色名 - 比如 "red"
- 十六进制值 - 比如 "#ff0000"
- RGB 值 - 比如 "rgb(255,0,0)"

查看 [CSS 颜色值](# CSS颜色)，以获取可能颜色值的完整列表。

页面的默认文本颜色是在 body 选择器中定义的。

#### 实例

```css
body {
  color: blue;
}

h1 {
  color: green;
}
```

------

### 文本颜色和背景色

在本例中，我们定义了 background-color 属性和 color 属性：

#### 实例

```css
body {
  background-color: lightgrey;
  color: blue;
}

h1 {
  background-color: black;
  color: white;
}
```

------

### CSS文本对齐

#### 文本对齐

text-align 属性用于设置文本的水平对齐方式。

文本可以左对齐或右对齐，或居中对齐。

下例展示了居中对齐以及左右对齐的文本（如果文本方向是从左到右，则默认为左对齐；如果文本方向是从右到左，则默认是右对齐）：

##### 实例1

```css
h1 {
  text-align: center;
}

h2 {
  text-align: left;
}

h3 {
  text-align: right;
}
```

> 当 text-align 属性设置为 "justify" 后，将拉伸每一行，以使每一行具有相等的宽度，并且左右边距是直的（就像在杂志和报纸中）

##### 实例2

```css
div {
  text-align: justify;
}
```

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-36-08.png)

------

#### 文本方向

direction 和 unicode-bidi 属性可用于更改元素的文本方向：

##### 实例

```css
p {
  direction: rtl;
  unicode-bidi: bidi-override;
}
```

------

#### 垂直对齐

vertical-align 属性设置元素的垂直对齐方式。

本例演示如何设置文本中图像的垂直对齐方式：

##### 实例

```css
img.top {
  vertical-align: top;
}

img.middle {
  vertical-align: middle;
}

img.bottom {
  vertical-align: bottom;
}
```

------

### 文本装饰

------

#### 文字装饰

> text-decoration 属性用于设置或删除文本装饰。
>
> text-decoration: none; 通常用于从链接上删除下划线：

##### 实例1

```css
a {
  text-decoration: none;
}
```

其他 text-decoration 值用于装饰文本：

##### 实例2

```css
h1 {
  text-decoration: overline;//上划线
}

h2 {
  text-decoration: line-through;//删除线
}

h3 {
  text-decoration: underline;//下划线
}
```

> **注释：**建议不要在非链接文本加下划线，因为这经常会使读者感到困惑。

------

### 文本转换

text-transform 属性用于指定文本中的大写和小写字母。

它可用于将所有内容转换为大写或小写字母，或将每个单词的首字母大写：

#### 实例

```css
p.uppercase {
  text-transform: uppercase;
}

p.lowercase {
  text-transform: lowercase;
}

p.capitalize {
  text-transform: capitalize;
}
```

------

### CSS文字间距

------

#### 文字缩进

text-indent 属性用于指定文本第一行的缩进：

##### 实例

```css
p {
  text-indent: 50px;
}
```

------

#### 字母间距

letter-spacing 属性用于指定文本中字符之间的间距。

下例演示如何增加或减少字符之间的间距：

##### 实例

```css
h1 {
  letter-spacing: 3px;
}

h2 {
  letter-spacing: -3px;
}
```

------

#### 行高

line-height 属性用于指定行之间的间距：

##### 实例

```css
p.small {
  line-height: 0.8;
}

p.big {
  line-height: 1.8;
}
```

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-53-13.png)

------

#### 字间距

word-spacing 属性用于指定文本中单词之间的间距。

下面演示如何增加或减少单词之间的间距：

##### 实例

```css
h1 {
  word-spacing: 10px;
}

h2 {
  word-spacing: -5px;
}
```

------

#### 空白

white-space 属性指定元素内部空白的处理方式。

此例演示如何禁用元素内的文本换行：

##### 实例

```css
p {
  white-space: nowrap;
}
```

------

### CSS文本阴影

------

#### 文本阴影

> text-shadow 属性为文本添加阴影。

最简单的用法是只指定水平阴影（2px）和垂直阴影（2px）：

文字阴影效果！

##### 实例1

```css
h1 {
  text-shadow: 2px 2px;
}
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-57-25.png" style="zoom:200%;" />

接下来，向阴影添加颜色（红色）：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-58-25.png"  />

##### 实例2

```css
h1 {
  text-shadow: 2px 2px red;
}
```

然后，向阴影添加模糊效果（5px）：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_13-59-17.png" style="zoom:150%;" />

##### 实例3

```css
h1 {
  text-shadow: 2px 2px 5px red;
}
```

**提示：**请访问 [CSS 字体](# CSS 字体) 一章，学习如何更改字体、文本大小和文本样式。

**提示：**请访问 [CSS 文本效果](# CSS 文本效果) 一章，学习如何实现不同的文本效果。

------

#### 所有 CSS 文本属性

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-02-32.png" style="zoom:150%;" />

------

## CSS颜色

### 悉知CSS 颜色

------

> **指定颜色是通过使用预定义的颜色名称，或 RGB、HEX、HSL、RGBA、HSLA 值。**

------

### CSS 颜色名

在 CSS 中，可以使用颜色名称来指定颜色：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-04-12.png)

------

### CSS 背景色

您可以为 HTML 元素设置背景色：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-05-33.png)

#### 实例

```css
<h1 style="background-color:DodgerBlue;">China</h1>
<p style="background-color:Tomato;">China is a great country!</p>
```

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-06-21.png)

------

### CSS 文本颜色

您可以设置文本的颜色：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-07-19.png)

#### 实例

```css
<h1 style="color:Tomato;">China</h1>
<p style="color:DodgerBlue;">China is a great country!</p>
<p style="color:MediumSeaGreen;">China, officially the People's Republic of China...</p>
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-07-59.png" style="zoom:150%;" />

------

### CSS 边框颜色

您可以设置边框的颜色：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-08-29.png" style="zoom:150%;" />

#### 实例

```css
<h1 style="border:2px solid Tomato;">Hello World</h1>
<h1 style="border:2px solid DodgerBlue;">Hello World</h1>
<h1 style="border:2px solid Violet;">Hello World</h1>
```

------

### CSS 颜色值

在 CSS 中，还可以使用 RGB 值、HEX 值、HSL 值、RGBA 值或者 HSLA 值来指定颜色：

与颜色名 "Tomato" 等效：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-10-03.png" style="zoom:150%;" />

与颜色名 "Tomato" 等效，但是透明度为 50%：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-10-49.png" style="zoom:150%;" />

#### <h3>实例</h3>

```css
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>

<h1 style="background-color:rgba(255, 99, 71, 0.5);">...</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">...</h1>
```

了解有关颜色值的更多信息

在下一节中，您将学习有关 [RGB](# CSS RGB 颜色)、[HEX](# CSS HEX 颜色) 和 [HSL](# CSS HSL 颜色) 的更多知识。

------

### CSS RGB 颜色

------

#### RGB 值

在 CSS 中，可以使用下面的公式将颜色指定为 RGB 值：

rgb(*red*, *green*, *blue*)

每个参数 (*red*、*green* 以及 *blue*) 定义了 0 到 255 之间的颜色强度。

例如，rgb(255, 0, 0) 显示为红色，因为红色设置为最大值（255），其他设置为 0。

要显示黑色，请将所有颜色参数设置为 0，如下所示：rgb(0, 0, 0)。

要显示白色，请将所有颜色参数设置为 255，如下所示：rgb(255, 255, 255)。

请通过混合以下 RGB 值来进行实验：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-16-05.png)

#### 	实例1

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-17-00.png)

通常为所有 3 个光源使用相等的值来定义灰色阴影：

#### 实例2

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-18-51.png" style="zoom:150%;" />

------

### RGBA 值

RGBA 颜色值是具有 alpha 通道的 RGB 颜色值的扩展 - 它指定了颜色的不透明度。

RGBA 颜色值指定为：

>  rgba(*red*, *green*, *blue*, *alpha*)

*alpha* 参数是介于 0.0（完全透明）和 1.0（完全不透明）之间的数字：

请通过混合以下 RGBA 值来进行实验：

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-19-34.png)

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-20-14.png" style="zoom:150%;" />

------

### CSS HEX 颜色

------

#### HEX 值

在 CSS 中，可以使用以下格式的十六进制值指定颜色：

> rrggbb

其中 rr（红色）、gg（绿色）和 bb（蓝色）是介于 00 和 ff 之间的十六进制值（与十进制 0-255 相同）。

例如，#ff0000 显示为红色，因为红色设置为最大值（ff），其他设置为最小值（00）。

请通过混合以下十六进制值来进行实验：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-21-42.png" style="zoom:150%;" />

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-22-27.png" style="zoom:150%;" />

通常为所有 3 个光源使用相等的值来定义灰色阴影：

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-23-02.png" style="zoom:150%;" />

------

### CSS HSL 颜色

------

#### HSL 值

在 CSS 中，可以使用色相、饱和度和明度（HSL）来指定颜色，格式如下：

>  hsla(*hue*, *saturation*, *lightness*)

色相（*hue*）是色轮上从 0 到 360 的度数。0 是红色，120 是绿色，240 是蓝色。

饱和度（*saturation*）是一个百分比值，0％ 表示灰色阴影，而 100％ 是全色。

亮度（*lightness*）也是百分比，0％ 是黑色，50％ 是既不明也不暗，100％是白色。

请通过混合以下 HSL 值来进行实验：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-23-49.png" style="zoom:150%;" />

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-24-16.png" style="zoom:150%;" />

------

### 饱和度

饱和度可以描述为颜色的强度。

100％ 是纯色，没有灰色阴影

50％ 是 50％ 灰色，但是您仍然可以看到颜色。

0％ 是完全灰色，您无法再看到颜色。

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-25-02.png" style="zoom:150%;" />

------

### 亮度

颜色的明暗度可以描述为要赋予颜色多少光，其中 0％ 表示不亮（黑色），50％ 表示 50％ 亮（既不暗也不亮），100％ 表示全明（白）。

#### 实例1

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-25-31.png" style="zoom:150%;" />

通常通过将色调和饱和度设置为 0 来定义灰色阴影，并将亮度从 0％ 到 100％ 进行调整可以得到更深/更浅的阴影：

#### 实例2

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-25-56.png" style="zoom:150%;" />

------

### HSLA 值

HSLA 颜色值是带有 Alpha 通道的 HSL 颜色值的扩展 - 它指定了颜色的不透明度。

HSLA 颜色值指定为：

>  hsla(*hue*, *saturation*, *lightness*, *alpha*)

*alpha* 参数是介于 0.0（完全透明）和 1.0（完全不透明）之间的数字：

请通过混合以下 HSLA 值进行实验：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-26-26.png" style="zoom:150%;" />

#### 实例

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-02-12_14-26-43.png" style="zoom:150%;" />

------

## CSS背景

### CSS背景

**CSS 背景属性用于定义元素的背景效果。**

#### CSS background-color

background-color 属性指定元素的背景色。

##### 实例

页面的背景色设置如下：

```css
 body{
            background-color: pink;
        }
```

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-03-07_10-31-32.png" style="zoom:60%;" />

通过 CSS，颜色通常由以下方式指定：

> - 有效的颜色名称 - 比如 "red"
> - 十六进制值 - 比如 "#ff0000"
> - RGB 值 - 比如 "rgb(255,0,0)"

------

#### 其他元素

您可以为任何 HTML 元素设置背景颜色：

##### 实例

在这里，<h1>、<p> 和 <div> 元素将拥有不同的背景色：

```css
h1 {
  background-color: green;
}

div {
  background-color: lightblue;
}

p {
  background-color: yellow;
}
```

------

#### 不透明度 / 透明度

opacity 属性指定元素的不透明度/透明度。取值范围为 0.0 - 1.0。值越低，越透明：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-03-07_10-37-33.png" style="zoom:80%;" />

```css
div {
  background-color: green;
  opacity: 0.3;
}
```

**注意：**使用 **opacity** 属性为元素的背景添加透明度时，其所有子元素都继承相同的透明度。这可能会使完全透明的元素内的文本难以阅读。

------

#### 使用 RGBA 的透明度

如果您不希望对子元素应用不透明度，例如上面的例子，请使用 *RGBA* 颜色值。下面的例子设置背景色而不是文本的不透明度：

<img src="C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-03-07_10-40-44.png" style="zoom:80%;" />

实例

```css
div {
  background: rgba(0, 128, 0, 0.3) /* 30% 不透明度的绿色背景 */
}
```

------

### CSS背景图像

background-image 属性指定用作元素背景的图像。

默认情况下，图像会重复，以覆盖整个元素。

#### 实例1

页面的背景图像可以像这样设置：

```css
body {
  background-image: url("paper.gif");
}
```

**注意：**使用背景图像时，请使用不会干扰文本的图像。

还可以为特定元素设置背景图像，例如 <p> 元素：

#### 实例2

```css
p {
  background-image: url("paper.gif");
}
```

------

### CSS背景重复

#### CSS background-repeat

默认情况下，background-image 属性在水平和垂直方向上都重复图像。

某些图像应只适合水平或垂直方向上重复，否则它们看起来会很奇怪，如下所示：

##### 实例1

```css
body {
  background-image: url("gradient_bg.png");
}
```

如果上面的图像仅在水平方向重复 (background-repeat: repeat-x;)，则背景看起来会更好：

##### 实例2

```css
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```

------

#### CSS background-repeat: no-repeat

background-repeat 属性还可指定只显示一次背景图像：

##### 实例

背景图像仅显示一次：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
}
```

------

#### CSS background-position

background-position 属性用于指定背景图像的位置。

##### 实例

把背景图片放在右上角：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

------

### CSS背景附着

#### CSS background-attachment

background-attachment 属性指定背景图像是应该滚动还是固定的（不会随页面的其余部分一起滚动）：

##### 实例1

指定应该固定背景图像：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: fixed;
}
```

##### 实例2

指定背景图像应随页面的其余部分一起滚动：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: scroll;
}
```

------

### CSS背景简写

#### CSS background - 简写属性

如需缩短代码，也可以在一个属性中指定所有背景属性。它被称为简写属性。

而不是这样写：

```css
body {
  background-color: #ffffff;
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

您能够使用简写属性 `background`：

##### 实例

使用简写属性在一条声明中设置背景属性：

```css
body {
  background: #ffffff url("tree.png") no-repeat right top;
}
```

**在使用简写属性时，属性值的顺序为：**

> - background-color
> - background-image
> - background-repeat
> - background-attachment
> - background-position

​	属性值之一缺失并不要紧，只要按照此顺序设置其他值即可。请注意，在上面的例子	中，我们没有使用 background-attachment 属性，因为它没有值。

#### 所有CSS背景属性

![](C:\Users\lemon\Pictures\截图6（CSS）\Snipaste_2022-03-07_12-12-55.png)