# 一、认识WEB

**「网页」**主要是由`文字`、`图像`和`超链接`等元素构成，当然除了这些元素，网页中还可以包括音频、视频以及Flash等。

**「浏览器」**是网页显示、运行的平台。

**「浏览器内核」**(排版引擎、解释引擎、渲染引擎)

> 负责读取网页内容，整理讯息，计算网页的显示方式并显示页面。

| 浏览器  |      内核      | 备注                                                         |
| :------ | :------------: | :----------------------------------------------------------- |
| IE      |    Trident     | IE、猎豹安全、360极速浏览器、百度浏览器                      |
| firefox |     Gecko      | 可惜这几年已经没落了，打开速度慢、升级频繁、猪一样的队友flash、神一样的对手chrome。 |
| Safari  |     webkit     | 现在很多人错误地把 webkit 叫做 chrome内核（即使 chrome内核已经是 blink 了）。苹果感觉像被别人抢了媳妇，都哭晕在厕所里面了。 |
| chrome  | Chromium/Blink | 在 Chromium 项目中研发 Blink 渲染引擎（即浏览器核心），内置于 Chrome 浏览器之中。Blink 其实是 WebKit 的分支。大部分国产浏览器最新版都采用Blink内核。二次开发 |
| Opera   |     blink      | 现在跟随chrome用blink内核。                                  |

### Web标准

**「构成」**👉 **结构标准，表现标准和行为标准**

- 结构标准用于对网页元素进行整理和分类(HTML)
- 表现标准用于设置网页元素的版式、颜色、大小等外观属性(CSS)
- 行为标准用于对网页模型的定义及交互的编写(JavaScript)

**「Web标准的优点」**👇

- 易于维护：只需更改CSS文件，就可以改变整站的样式
- 页面响应快：HTML文档体积变小，响应时间短
- 可访问性：语义化的HTML（结构和表现相分离的HTML）编写的网页文件，更容易被屏幕阅读器识别
- 设备兼容性：不同的样式表可以让网页在不同的设备上呈现不同的样式
- 搜索引擎：语义化的HTML能更容易被搜索引擎解析，提升排名

# 二、HTML初识

## HTML初识

HTML 是用来描述网页的一种语言。

- HTML 指的是超文本标记语言 (**H**yper **T**ext **M**arkup **L**anguage)
- HTML 不是一种编程语言，而是一种*标记语言* (markup language)
- 标记语言是一套*标记标签* (markup tag)
- HTML 使用*标记标签*来描述网页

**「HTML」**(Hyper Text Markup Language):超文本标记语言

**「所谓超文本，有2层含义：」**

- 因为它可以加入图片、声音、动画、多媒体等内容（超越文本限制 ）
- 不仅如此，它还可以从一个文件跳转到另一个文件，与世界各地主机的文件连接（超级链接文本）。

**「HTML骨架格式」**

```
<!-- 页面中最大的标签 根标签 -->
<html>
    <!-- 头部标签 -->
    <head>     
        <!-- 标题标签 -->
        <title></title> 
    </head>
    <!-- 文档的主体 -->
    <body>
    </body>
</html>
```

**「团队约定大小写」**

- HTML标签名、类名、标签属性和大部分属性值统一用小写

**「HTML元素标签分类」**

- 常规元素(双标签)
- 空元素(单标签)

```
  常规元素(双标签)
  <标签名> 内容 </标签名>   比如<body>我是文字</body>

  空元素(单标签)
  <标签名 />  比如 <br />或<br>
```

**「HTML标签关系」**

- 嵌套关系父子级包含关系

- 并列关系兄弟级并列关系

- - 如果两个标签之间的关系是嵌套关系，子元素最好缩进一个tab键的身位（一个tab是4个空格）。如果是并列关系，最好上下对齐。

### 文档类型<!DOCTYPE >

**「文档类型」**用来说明你用的XHTML或者HTML是什么版本。<!DOCTYPE html>告诉浏览器按照HTML5标准解析页面。

### 页面语言lang

lang指定该html标签内容所用的语言

```
  <html lang="en">  
  en 定义语言为英语 zh-CN定义语言为中文
```

**「lang的作用」**

- 根据根据lang属性来设定不同语言的css样式，或者字体
- 告诉搜索引擎做精确的识别
- 让语法检查程序做语言识别
- 帮助翻译工具做识别
- 帮助网页阅读程序做识别

### 字符集

**「字符集」**(Character set)是多个字符的集合,计算机要准确的处理各种字符集文字，需要进行字符编码，以便计算机能够识别和存储各种文字。

- UTF-8是目前最常用的字符集编码方式
- 让 html 文件是以 UTF-8 编码保存的， 浏览器根据编码去解码对应的html内容。

```
  <meta charset="UTF-8" />
```

**「meta viewport的用法」**
  通常viewport是指视窗、视口。浏览器上(也可能是一个app中的webview)用来显示网页的那部分区域。在移动端和pc端视口是不同的，pc端的视口是浏览器窗口区域，而在移动端有三个不同的视口概念：布局视口、视觉视口、理想视口

  meta有两个属性name 和 http-equiv

**name属性的取值**

- keywords(关键字) 告诉搜索引擎，该网页的关键字
- description(网站内容描述) 用于告诉搜索引擎，你网站的主要内容。
- viewport(移动端的窗口)
- robots(定义搜索引擎爬虫的索引方式) robots用来告诉爬虫哪些页面需要索引，哪些页面不需要索引
- author(作者)
- generator(网页制作软件）
- copyright(版权)

**http-equiv有以下参数**

http-equiv相当于http的文件头作用，它可以向浏览器传回一些有用的信息，以帮助正确和精确地显示网页内容

- content-Type 设定网页字符集(Html4用法，不推荐)
- Expires(期限) ,可以用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输。
- Pragma(cache模式),是用于设定禁止浏览器从本地机的缓存中调阅页面内容，设定后一旦离开网页就无法从Cache中再调出
- Refresh(刷新),自动刷新并指向新页面。
- cache-control（请求和响应遵循的缓存机制）

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

# 三、HTML 标签

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

- HTML 标签是由*尖括号*包围的关键词，比如 <html>
- HTML 标签通常是*成对出现*的，比如 <b> 和 </b>
- 标签对中的第一个标签是*开始标签*，第二个标签是*结束标签*
- 开始和结束标签也被称为*开放标签*和*闭合标签*

## HTML标签的语义化

- 方便代码的阅读和维护，样式丢失的时候能让页面呈现清晰的结构。
- 有利于SEO，搜索引擎根据标签来确定上下文和各个关键字的权重。
- 方便其他设备解析，如盲人阅读器根据语义渲染网页

**「拓展」** 标签：规定页面上所有链接的默认 URL 和设置整体链接的打开状态

```html
<head>
    <base href="http://www.baidu.com" target="_blank">
    <base target="_self">
</head>
<body>
    <a href="">测试</a> 跳转到 百度
</body>
```

------



## HTML 文档 = 网页

- HTML 文档*描述网页*
- HTML 文档*包含 HTML 标签*和纯文本
- HTML 文档也被称为*网页*

Web 浏览器的作用是读取 HTML 文档，并以网页的形式显示出它们。浏览器不会显示 HTML 标签，而是使用标签来解释页面的内容：

```
<html>
<body>

<h1>我的第一个标题</h1>

<p>我的第一个段落。</p>

</body>
</html>
```

### 例子解释

- <html> 与 </html> 之间的文本描述网页

- <body> 与 </body> 之间的文本是可见的页面内容

- <h1> 与 </h1> 之间的文本被显示为标题

- <p> 与 </p> 之间的文本被显示为段落

------









# 四、走进HTML



## HTML编辑器

------

​	

### 使用 Notepad 或 TextEdit 来编写 HTML

可以使用专业的 HTML 编辑器来编辑 HTML：

- Adobe Dreamweaver
- Microsoft Expression Web
- CoffeeCup HTML Editor

不过，我们同时推荐使用文本编辑器来学习 HTML，比如 Notepad (PC) 或 TextEdit (Mac)。我们相信，使用一款简单的文本编辑器是学习 HTML 的好方法。

通过记事本，依照以下四步来创建您的第一张网页

------



#### 步骤一：Visual stuidio vsode

如何启动 Visual stuidio vsode：

开始
  所有程序
    附件
    Visual stuidio vsode

------



#### 步骤二：用Visual stuidio vsode来编辑 HTML

在Visual stuidio vsode中键入 HTML 代码：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_16-01-23.png" />

------



#### 步骤三：保存 HTML

在记事本的文件菜单选择“另存为”。

当您保存 HTML 文件时，既可以使用 .htm 也可以使用 .html 扩展名。两者没有区别，完全根据您的喜好。

在一个容易记忆的文件夹中保存这个文件

------



#### 步骤四：在浏览器中运行这个 HTML 文件

启动您的浏览器，然后选择“文件”菜单的“打开文件”命令，或者直接在文件夹中双击您的 HTML 文件。

结果应该类似这样：

![](https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_16-01-32.png)

------



## HTML基础

### 基本的 HTML 标签 - 四个实例

------



#### HTML 标题

HTML 标题（Heading）是通过 <h1> - <h6> 等标签进行定义的。

##### 实例

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

------



#### HTML 段落

 **HTML 段落是通过 <p> 标签进行定义的。**

##### 实例

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

------



#### HTML链接

**HTML 链接是通过 <a> 标签进行定义的。**

##### 实例

```html
<a href="http://www.baidu.com">This is a link</a>
```



**注释：**在 href 属性中指定链接的地址。

------



### HTML 图像

**HTML 图像是通过 <img> 标签进行定义的。**

##### 实例

```html
<img src="bg.jpg" width="104" height="142" />
```

------



## HTML元素

**HTML 文档是由 HTML 元素定义的。**

------



### HTML元素简介

**HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。**

| 开始标签                | 元素内容            | 结束标签 |
| :---------------------- | :------------------ | :------- |
| <p>                     | This is a paragraph | </p>     |
| <a href="default.htm" > | This is a link      | </a>     |
| <br />                  |                     |          |

**注释：**开始标签常被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

------



### HTML 元素语法

- HTML 元素以*开始标签*起始

- HTML 元素以*结束标签*终止

- *元素的内容*是开始标签与结束标签之间的内容

- 某些 HTML 元素具有*空内容（empty content）*

- 空元素*在开始标签中进行关闭*（以开始标签的结束而结束）

- 大多数 HTML 元素可拥有*属性*

  ------

  

### 嵌套的 HTML 元素

大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）。

**HTML 文档由嵌套的 HTML 元素构成。**

#### HTML 文档实例

```html
<html>

<body>
<p>This is my first paragraph.</p>
</body>

</html>
```

上面的例子包含三个 HTML 元素。

------



### HTML 实例解释

####  <p>元素 p：

```html
<p>This is my first paragraph.</p>
```

这个 <p> 元素定义了 HTML 文档中的一个段落。

这个元素拥有一个开始标签 <p>，以及一个结束标签 </p>。

元素内容是：This is my first paragraph。

#### <body> 元素 body：

```html
<body>
<p>This is my first paragraph.</p>
</body>
```

<body> 元素定义了 HTML 文档的主体。

这个元素拥有一个开始标签 <body>，以及一个结束标签 </body>。

元素内容是另一个 HTML 元素（p 元素）。

#### <html> 元素 html：

```html
<html>

<body>
<p>This is my first paragraph.</p>
</body>

</html>
```

> <html> 元素定义了整个 HTML 文档。
>
> 这个元素拥有一个开始标签 <html>，以及一个结束标签 </html>。
>
> 元素内容是另一个 HTML 元素（body 元素）。

------



### 不要忘记结束标签

即使您忘记了使用结束标签，大多数浏览器也会正确地显示 HTML：

```html
<p>This is a paragraph
<p>This is a paragraph
```



上面的例子在大多数浏览器中都没问题，但不要依赖这种做法。忘记使用结束标签会产生不可预料的结果或错误。

**注释：**未来的 HTML 版本不允许省略结束标签。

------



### 空的 HTML 元素

> 没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。

> <br> 就是没有关闭标签的空元素（<br标签定义换行）。

在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。

在开始标签中添加斜杠，比如 <br />，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。

> 即使 <br> 在所有浏览器中都是有效的，但使用 <br /> 其实是更长远的保障。

------



### HTML 提示：使用小写标签

HTML 标签对大小写不敏感：<P> 等同于 <p>。许多网站都使用大写的 HTML 标签。

万维网联盟（W3C）在 HTML 4 中*推荐*使用小写，而在未来 (X)HTML 版本中*强制*使用小写。

------



## HTML 属性

------



### HTML属性悉知

------

**属性为 HTML 元素提供附加信息**

------

HTML 标签可以拥有*属性*。属性提供了有关 HTML 元素的*更多的信息*。

属性总是以名称/值对的形式出现，比如：*name="value"*。

属性总是在 HTML 元素的*开始标签*中规定。

------



### 属性实例

HTML 链接由 <a> 标签定义。链接的地址在 href 属性中指定：

```html
<a href="http://www.baidu.com">This is a link</a>
```

------

### 更多 HTML 属性实例

#### 属性例子 1:

<h1> 定义标题的开始。

<h1 align="center"> 拥有关于对齐方式的附加信息。

[TIY : 居中排列标题](https://www.w3school.com.cn/tiy/t.asp?f=eg_html_header)

#### 属性例子 2:

<body> 定义 HTML 文档的主体。

<body bgcolor="yellow"> 拥有关于背景颜色的附加信息。

[TIY : 背景颜色](https://www.w3school.com.cn/tiy/t.asp?f=eg_html_bgcolor)

#### 属性例子 3:

<table> 定义 HTML 表格。

<table border="1"> 拥有关于表格边框的附加信息。

------

### HTML 提示：使用小写属性

属性和属性值对大小写*不敏感*。

不过，万维网联盟在其 HTML 4 推荐标准中推荐小写的属性/属性值。

而新版本的 (X)HTML 要求使用小写属性。

------

### 始终为属性值加引号

属性值应该始终被包括在引号内。双引号是最常用的，不过使用单引号也没有问题。

在某些个别的情况下，比如属性值本身就含有双引号，那么您必须使用单引号，例如：

```html
name='Bill "HelloWorld" Gates'
```

------

### HTML 属性参考手册

完整的 HTML 参考手册提供了每个 HTML 元素可使用的合法属性的完整列表：

[完整的 HTML 参考手册](https://www.w3school.com.cn/tags/index.asp)

下面列出了适用于大多数 HTML 元素的属性：

| 属性  | 值                 | 描述                                     |
| :---- | :----------------- | :--------------------------------------- |
| class | *classname*        | 规定元素的类名（classname）              |
| id    | *id*               | 规定元素的唯一 id                        |
| style | *style_definition* | 规定元素的行内样式（inline style）       |
| title | *text*             | 规定元素的额外信息（可在工具提示中显示） |

如需更多关于标准属性的信息，请访问：

[HTML 标准属性参考手册](https://www.w3school.com.cn/tags/html_ref_standardattributes.asp)

------



## HTML 标题

------

**在 HTML 文档中，标题很重要。**

------

### HTML 标题

标题（Heading）是通过 <h1> - <h6> 等标签进行定义的。

<h1> 定义最大的标题。<h6> 定义最小的标题。

#### 实例

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

> **注释：**浏览器会自动地在标题的前后添加空行。
>
> **注释：**默认情况下，HTML 会自动地在块级元素前后添加一个额外的空行，比如段落、标题元素前后。

------

### 标题很重要

请确保将 HTML heading 标签只用于标题。不要仅仅是为了产生粗体或大号的文本而使用标题。

搜索引擎使用标题为您的网页的结构和内容编制索引。

因为用户可以通过标题来快速浏览您的网页，所以用标题来呈现文档结构是很重要的。

应该将 h1 用作主标题（最重要的），其后是 h2（次重要的），再其次是 h3，以此类推。

------

### HTML 水平线

<hr /> 标签在 HTML 页面中创建水平线。

hr 元素可用于分隔内容。

#### 实例

```html
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
```

------

### HTML 注释

可以将注释插入 HTML 代码中，这样可以提高其可读性，使代码更易被人理解。浏览器会忽略注释，也不会显示它们。

注释是这样写的：

### 实例

```html
<!-- This is a comment -->
```

------

> **注释：**开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要。
>
> **提示：**合理地使用注释可以对未来的代码编辑工作产生帮助。

------

### HTML 提示 - 如何查看源代码

您一定曾经在看到某个网页时惊叹道 “WOW! 这是如何实现的？”

如果您想找到其中的奥秘，只需要单击右键，然后选择“检查”（IE）或“查看页面源代码”（Firefox），其他浏览器的做法也是类似的。这么做会打开一个包含页面 HTML 代码的窗口。

------

## HTML 段落

------

**可以把 HTML 文档分割为若干段落。**

------

### HTML 段落

段落是通过 <p> 标签定义的。

#### 实例

```html
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

> **注释：**浏览器会自动地在段落的前后添加空行。（<p> 是块级元素）
>
> **提示：**使用空的段落标记 <p></p> 去插入一个空行是个坏习惯。用 <br /> 标签代替它！（但是不要用 <br />）

### 不要忘记结束标签

即使忘了使用结束标签，大多数浏览器也会正确地将 HTML 显示出来：

#### 实例

```html
<p>This is a paragraph
<p>This is another paragraph
```

> 上面的例子在大多数浏览器中都没问题，但不要依赖这种做法。忘记使用结束标签会产生意想不到的结果和错误。
>
> **注释：**在未来的 HTML 版本中，不允许省略结束标签。
>
> **提示：**通过结束标签来关闭 HTML 是一种经得起未来考验的 HTML 编写方法。清楚地标记某个元素在何处开始，并在何处结束，不论对您还是对浏览器来说，都会使代码更容易理解。

### HTML折行

如果您希望在不产生一个新段落的情况下进行换行（新行），请使用 <br /> 标签：

```html
<p>This is<br />a para<br />graph with line breaks</p>
```

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-31-54.png" style="zoom: 67%;" />

<br /> 元素是一个空的 HTML 元素。由于关闭标签没有任何意义，因此它没有结束标签。

------

### <br还是 <br />

> 您也许发现 <br与 <br /很相似。
>
> 在 XHTML、XML 以及未来的 HTML 版本中，不允许使用没有结束标签（闭合标签）的 HTML 元素。
>
> 即使 <br> 在所有浏览器中的显示都没有问题，使用 <br /> 也是*更长远的保障*。

------

### HTML 输出 - 有用的提示

我们无法确定 HTML 被显示的确切效果。屏幕的大小，以及对窗口的调整都可能导致不同的结果。

对于 HTML，您无法通过在 HTML 代码中添加额外的空格或换行来改变输出的效果。

> 当显示页面时，浏览器会移除*源代码中*多余的空格和空行。所有连续的空格或空行都会被算作一个空格。需要注意的是，HTML 代码中的所有连续的空行（换行）也被显示为一个空格。

## HTML 样式

------

### HTML 样式

------

style 属性用于改变 HTML 元素的样式。

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-40-19.png" style="zoom:67%;" />

​	

------

### HTML 的 style 属性

style 属性的作用：

**提供了一种改变所有 HTML 元素的样式的通用方法。**

样式是 HTML 4 引入的，它是一种新的首选的改变 HTML 元素样式的方式。通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义。

------

### 不赞成使用的标签和属性

在 HTML 4 中，有若干的标签和属性是被废弃的。被废弃（Deprecated）的意思是在未来版本的 HTML 和 XHTML 中将不支持这些标签和属性。

这里传达的信息很明确：请避免使用这些被废弃的标签和属性！

### 应该避免使用下面这些标签和属性：

| 标签                 | 描述               |
| :------------------- | :----------------- |
| <center>             | 定义居中的内容。   |
| <font> 和 <basefont> | 定义 HTML 字体。   |
| <s> 和 <strike>      | 定义删除线文本     |
| <u>                  | 定义下划线文本     |
| 属性                 | 描述               |
| align                | 定义文本的对齐方式 |
| bgcolor              | 定义背景颜色       |
| color                | 定义文本颜色       |

> 对于以上这些标签和属性：请使用样式代替！

------

#### HTML 样式实例 - 背景颜色

background-color 属性为元素定义了背景颜色：

```html
<html>

<body style="background-color:yellow">
<h2 style="background-color:red">This is a heading</h2>
<p style="background-color:green">This is a paragraph.</p>
</body>

</html>
```

**style 属性淘汰了“旧的” bgcolor 属性。**

------

#### HTML 样式实例 - 字体、颜色和尺寸

font-family、color 以及 font-size 属性分别定义元素中文本的字体系列、颜色和字体尺寸：

```html
<html>

<body>
<h1 style="font-family:verdana">A heading</h1>
<p style="font-family:arial;color:red;font-size:20px;">A paragraph.</p>
</body>

</html>
```

**style 属性淘汰了旧的 <font> 标签。**

------

#### TML 样式实例 - 文本对齐

text-align 属性规定了元素中文本的水平对齐方式：

```html
<html>

<body>
<h1 style="text-align:center">This is a heading</h1>
<p>The heading above is aligned to the center of this page.</p>
</body>

</html>
```

------

## HTML 文本格式化

------

**HTML 可定义很多供格式化输出的元素，比如粗体和斜体字。**

------

### 文本格式化标签

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-48-06.png" style="zoom:80%;" />

------

### “计算机输出”标签

------

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-48-51.png" style="zoom:80%;" />

------

### 引用、引用和术语定义

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-49-32.png" style="zoom:80%;" />

------

## HTML 引用

------

### HTML <q> 用于短的引用

HTML *<q>* 元素定义*短的引用*。

浏览器通常会为 <q> 元素包围*引号*。

#### 实例

```html
<p>WWF 的目标是：<q>构建人与自然和谐共存的世界。</q></p>
```

------

### 用于长引用的 HTML <blockquote>

HTML *<blockquote>* 元素定义被引用的节。

浏览器通常会对 <blockquote> 元素进行*缩进*处理。

#### 实例

```html
<p>以下内容引用自 WWF 的网站：</p>
<blockquote cite="http://www.worldwildlife.org/who/index.html">
五十年来，WWF 一直致力于保护自然界的未来。
世界领先的环保组织，WWF 工作于 100 个国家，
并得到美国一百二十万会员及全球近五百万会员的支持。
</blockquote>
```

------

### 用于缩略词的 HTML <abbr>

HTML *<abbr>* 元素定义*缩写*或首字母缩略语。

对缩写进行标记能够为浏览器、翻译系统以及搜索引擎提供有用的信息。

#### 实例

```html
<p><abbr title="World Health Organization">WHO</abbr> 成立于 1948 年。</p>
```

------

### 用于定义的 HTML <dfn>

HTML *<dfn>* 元素定义项目或缩写的*定义*。

<dfn> 的用法，按照 HTML5 标准中的描述，有点复杂：

1. 如果设置了 <dfn> 元素的 title 属性，则定义项目：

#### 实例

```html
<p><dfn title="World Health Organization">WHO</dfn> 成立于 1948 年。</p>
```

------

2. 如果 <dfn> 元素包含具有标题的 <abbr> 元素，则 title 定义项目：

#### 实例

```html
<p><dfn><abbr title="World Health Organization">WHO</abbr></dfn> 成立于 1948 年。</p>
```

------

3. 否则，<dfn> 文本内容即是项目，并且父元素包含定义。

#### 实例

```html
<p><dfn>WHO</dfn> World Health Organization 成立于 1948 年。</p>
```

**注释：**如果您希望简而化之，请使用第一条，或使用 <abbr> 代替。

------

### 用于联系信息的 HTML <address>

HTML *<address>* 元素定义文档或文章的联系信息（作者/拥有者）。

此元素通常以*斜体*显示。大多数浏览器会在此元素前后添加折行。

#### 实例

```html
<address>
Written by Donald Duck.<br> 
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address
```

------

### HTML 引文、引用和定义元素

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_17-58-28.png" style="zoom:80%;" />

------

## HTML注释

------

### HTML注释

------

**注释标签 <!-- 与 --> 用于在 HTML 插入注释。**

------

### HTML 注释标签

您能够通过如下语法向 HTML 源代码添加注释：

#### 实例

```html
<!-- 在此处写注释 -->
```

**注释：**在开始标签中有一个惊叹号，但是结束标签中没有。

浏览器不会显示注释，但是能够帮助记录您的 HTML 文档。

您可以利用注释在 HTML 中放置通知和提醒信息：

### 实例

```html
<!-- 这是一段注释 -->

<p>这是一个段落。</p>

<!-- 记得在此处添加信息 -->
```

------

### 条件注释

您也许会在 HTML 中偶尔发现条件注释：

```html
<!--[if IE 8]>
    .... some HTML here ....
<![endif]-->
```

条件注释定义只有 Internet Explorer 执行的 HTML 标签。

------

### 软件程序标签

各种 HTML 软件程序也能够生成 HTML 注释。

例如 <!--webbot bot--> 标签会被包围在由 FrontPage 和 Expression Web 创建的 HTML 注释中。

作为一项规则，这些标签的存在，有助于对创建这些标签的软件的支持。

------

## HTML 颜色

------

### HTML 颜色

**颜色由红色、绿色、蓝色混合而成。**

------

### 颜色值

颜色由一个十六进制符号来定义，这个符号由红色、绿色和蓝色的值组成（RGB）。

每种颜色的最小值是 0（十六进制：#00）。最大值是 255（十六进制：#FF）。

这个表格给出了由三种颜色混合而成的具体效果：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-04-16.png" style="zoom:80%;" />

------

### 颜色名

大多数的浏览器都支持颜色名集合。

**提示：**仅仅有 16 种颜色名被 W3C 的 HTML4.0 标准所支持。它们是：aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, purple, red, silver, teal, white, yellow。

如果需要使用其它的颜色，需要使用十六进制的颜色值。

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-04-45.png" style="zoom:80%;" />

------

### Web安全色

数年以前，当大多数计算机仅支持 256 种颜色的时候，一系列 216 种 Web 安全色作为 Web 标准被建议使用。其中的原因是，微软和 Mac 操作系统使用了 40 种不同的保留的固定系统颜色（双方大约各使用 20 种）。

我们不确定如今这么做的意义有多大，因为越来越多的计算机有能力处理数百万种颜色，不过做选择的还是你自己。

#### 216 跨平台色

最初，216 跨平台 web 安全色被用来确保：当计算机使用 256 色调色板时，所有的计算机能够正确地显示所有的颜色。

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-05-58.png" style="zoom:67%;" />

------

## HTML颜色名

### HTML 颜色名

------

**提示：**仅有 16 种*颜色名*被 W3C 的 HTML 4.0 标准支持，它们是：aqua、black、blue、fuchsia、gray、green、lime、maroon、navy、olive、purple、red、silver、teal、white、yellow。

> 如果使用其它颜色的话，就应该使用*十六进制的颜色值*。

------

### 颜色名列表

单击一个颜色名或者 16 进制值，就可以查看与不同文字颜色搭配的背景颜色。

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-07-59.png" style="zoom:80%;" />

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-08-17.png" style="zoom:80%;" />

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-08-32.png" style="zoom:80%;" />

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-08-54.png" style="zoom:80%;" />

<img src="C:\Users\lemon\Pictures\截图5（2022）\Snipaste_2022-02-05_18-09-09.png" style="zoom:80%;" />

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-09-21.png" style="zoom:80%;" />

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_18-09-31.png" style="zoom:80%;" />

<img src="C:\Users\lemon\Pictures\截图5（2022）\Snipaste_2022-02-05_18-09-42.png" style="zoom:80%;" />

------

## HTML CSS

### HTML CSS

------

**通过使用 HTML4.0，所有的格式化代码均可移出 HTML 文档，然后移入一个独立的样式表。**

------

### 如何使用样式

当浏览器读到一个样式表，它就会按照这个样式表来对文档进行格式化。有以下三种方式来插入样式表：

#### 外部样式表

当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。使用外部样式表，你就可以通过更改一个文件来改变整个站点的外观。

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

#### 内部样式表

当单个文件需要特别样式时，就可以使用内部样式表。你可以在 head 部分通过 <style> 标签定义内部样式表。

```html
<head>

<style type="text/css">
body {background-color: red}
p {margin-left: 20px}
</style>
</head>
```

#### 内联样式

当特殊的样式需要应用到个别元素时，就可以使用内联样式。 使用内联样式的方法是在相关的标签中使用样式属性。样式属性可以包含任何 CSS 属性。以下实例显示出如何改变段落的颜色和左外边距。

```html
<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
```

------

## HTML 链接

### HTML 链接

------

**HTML 使用超级链接与网络上的另一个文档相连。**

**几乎可以在所有的网页中找到链接。点击链接可以从一张页面跳转到另一张页面。**

------

### HTML 超链接（链接）

超链接可以是一个字，一个词，或者一组词，也可以是一幅图像，您可以点击这些内容来跳转到新的文档或者当前文档中的某个部分。

当您把鼠标指针移动到网页中的某个链接上时，箭头会变为一只小手。

我们通过使用 <a> 标签在 HTML 中创建链接。

有两种使用 <a> 标签的方式：

1. 通过使用 href 属性 - 创建指向另一个文档的链接
2. 通过使用 name 属性 - 创建文档内的书签

------

### HTML 链接语法

链接的 HTML 代码很简单。它类似这样：

```html
<a href="url">Link text</a>
```

href 属性规定链接的目标。

开始标签和结束标签之间的文字被作为超级链接来显示。

#### 实例

```html
<a href="https://www.cnblogs.com/gaoziman">爱笑的Gao'博客</a>
```

上面这行代码显示为：[Visit W3School](https://www.cnblogs.com/gaoziman)

点击这个超链接会把用户带到 W3School 的首页。

**提示：**"链接文本" 不必一定是文本。图片或其他 HTML 元素都可以成为链接。

------

### HTML 链接 - target 属性

使用 Target 属性，你可以定义被链接的文档在何处显示。

下面的这行会在新窗口打开文档：

```html
<a href="https://www.cnblogs.com/gaoziman" target="_blank">爱笑的Gao'博客!</a>h
```

------

### HTML 链接 - name 属性

name 属性规定锚（anchor）的名称。

您可以使用 name 属性创建 HTML 页面中的书签。

书签不会以任何特殊方式显示，它对读者是不可见的。

当使用命名锚（named anchors）时，我们可以创建直接跳至该命名锚（比如页面中某个小节）的链接，这样使用者就无需不停地滚动页面来寻找他们需要的信息了。

#### 命名锚的语法：

```html
<a name="label">锚（显示在页面上的文本）</a>
```

**提示：**锚的名称可以是任何你喜欢的名字。

**提示：**您可以使用 id 属性来替代 name 属性，命名锚同样有效。

#### 实例

首先，我们在 HTML 文档中对锚进行命名（创建一个书签）：

```html
<a name="tips">基本的注意事项 - 有用的提示</a>
```

然后，我们在同一个文档中创建指向该锚的链接：

```html
<a href="#tips">有用的提示</a>
```

您也可以在其他页面中创建指向该锚的链接：

```html
<a href="https://www.cnblogs.com/gaoziman/html/html_links.asp#tips">有用的提示</a>
```

*锚点定位：通过创建锚点链接，用户能够快速定位到目标内容。**

```html
1. 使用相应的id名标注跳转目标的位置。 (找目标)
  <h3 id="two">第2集</h3> 

2. 使用<a href="#id名">链接文本</a>创建链接文本（被点击的） 
  <a href="#two">   
```

------

### HTML 链接标签

```html
<a href="跳转目标" target="目标窗口的弹出方式">文本或图像</a>
target="_self"  默认窗口弹出方式
target="_blank" 新窗口弹出
```

![](C:\Users\lemon\Pictures\截图5（2022）\Snipaste_2022-02-05_19-45-13.bmp)

------

## HTML 图像

------

**通过使用 HTML，可以在文档中显示图像。**

------

### 图像标签（<img>）和源属性（Src）

在 HTML 中，图像由 <img> 标签定义。

<img> 是空标签，意思是说，它只包含属性，并且没有闭合标签。

要在页面上显示图像，你需要使用源属性（src）。src 指 "source"。源属性的值是图像的 URL 地址。

定义图像的语法是：

```html
<img src="url" />
```

URL 指存储图像的位置。如果名为 "beat.gif" 的图像位于 www.baidu.com 的 images 目录中，那么其 URL 为 http://www.baidu.com/images/beat.gif。

> 浏览器将图像显示在文档中图像标签出现的地方。如果你将图像标签置于两个段落之间，那么浏览器会首先显示第一个段落，然后显示图片，最后显示第二段。

------

### 替换文本属性（Alt）

alt 属性用来为图像定义一串预备的可替换的文本。替换文本属性的值是用户定义的。

```html
<img src="boat.gif" alt="Big Boat">
```

> 当浏览器无法载入图像时，替换文本属性可告诉读者他们失去的信息。此时，浏览器将显示这个替代性的文本而不是图像。为页面上的图像都加上替换文本属性是个好习惯，这样有助于更好的显示信息，并且对于那些使用纯文本浏览器的人来说是非常有用的。

------

### 基本的注意事项 - 有用的提示：

假如某个 HTML 文件包含十个图像，那么为了正确显示这个页面，需要加载 11 个文件。加载图片是需要时间的，所以我们的建议是：慎用图片。

------

### 图像标签（img）

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-07-12.png" style="zoom:80%;" />

**注意：**

- 标签可以拥有多个属性，必须写在开始标签中，位于标签名后面。
- 属性之间不分先后顺序，标签名与属性、属性与属性之间均以空格分开。
- 采取  键值对 的格式  key="value"  的格式

------

## HTML 表格

### HTML 表格

------

**你可以使用 HTML 创建表格。**

------

### 表格

表格由 <table> 标签来定义。每个表格均有若干行（由 <tr> 标签定义），每行被分割为若干单元格（由 <td> 标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

```html
<table border="1">
<tr>
<td>row 1 ,cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>row 2, cell 1</td>
<td>row 2, cell 2</td>
</tr>
</table>
```

在浏览器显示如下：

| row 1, cell 1 | row 1, cell 2 |
| ------------- | ------------- |
| row 2, cell 1 | row 2, cell 2 |

注意：

table、tr、td，他们是创建表格的基本标签，缺一不可

- table用于定义一个表格标签。

- tr标签 用于定义表格中的行，必须嵌套在 table标签中。

- td 用于定义表格中的单元格，必须嵌套在<tr></tr>标签中。

- 字母 td 指表格数据（table data），即数据单元格的内容，现在我们明白，表格最合适的地方就是用来存储数据的。td像一个容器，可以容纳所有的元素。

  <img src="C:\Users\lemon\Pictures\截图5（2022）\Snipaste_2022-02-05_20-14-43.bmp" style="zoom:80%;" />

> 1. 每个表格由 table 标签开始。
>
> 2. 每个表格行由 tr 标签开始。
>
> 3. 每个表格数据由 td 标签开始。
>
> 4. **表头单元格标签th**:一般表头单元格位于表格的第一行或第一列，并且文本加粗居中,只需用表头标签<th></th>替代相应的单元格标签<td></td>即可。
>
> 5. **表格标题caption**通常这个标题会被居中且显示于表格之上。caption 标签必须紧随 table 标签之后。这个标签只存在 表格里面才有意义。你是风儿我是沙
>
>    ```html
>    <table>
>       <caption>我是表格标题</caption>
>    </table>
>    ```
>
>    

------

### 表格和边框属性

如果不定义边框属性，表格将不显示边框。有时这很有用，但是大多数时候，我们希望显示边框。

使用边框属性来显示一个带有边框的表格：

```html
<table border="1">
<tr>
<td>Row 1, cell 1</td>
<td>Row 1, cell 2</td>
</tr>
</table>
```

#### 表格属性

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-16-59.png" style="zoom:80%;" />

> 三参为0，平时开发的我们这三个参数   border  cellpadding  cellspacing 为  0

------

### 表格的表头

表格的表头使用 <th> 标签进行定义。

大多数浏览器会把表头显示为粗体居中的文本：

```html
<table border="1">
<tr>
<th>Heading</th>
<th>Another Heading</th>
</tr>
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>row 2, cell 1</td>
<td>row 2, cell 2</td>
</tr>
</table>
```

在浏览器显示如下：

| Heading       | Another Heading |
| ------------- | --------------- |
| row 1, cell 1 | row 1, cell 2   |
| row 2, cell 1 | row 2, cell 2   |

------

### 表格中的空单元格

在一些浏览器中，没有内容的表格单元显示得不太好。如果某个单元格是空的（没有内容），浏览器可能无法显示出这个单元格的边框。

```html
<table border="1">
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td></td>
<td>row 2, cell 2</td>
</tr>
</table>
```

浏览器可能会这样显示：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-19-26.png" style="zoom:150%;" />

**注意：**这个空的单元格的边框没有被显示出来。为了避免这种情况，在空单元格中添加一个空格占位符，就可以将边框显示出来

```html
<table border="1">
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>row 2, cell 2</td>
</tr>
</table>
```

在浏览器中显示如下：

| row 1, cell 1 | row 1, cell 2 |
| ------------- | ------------- |
|               | row 2, cell 2 |

------

### 表格标签

![](https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-21-26.png)

------

## HTML 列表

### HTML 列表

------

**HTML 支持有序、无序和定义列表**

------

### 无序列表

无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记。

无序列表始于 <ul> 标签。每个列表项始于 <li>。

```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
</ul>
```

浏览器显示如下：

- Coffee
- Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

------

### 有序列表

同样，有序列表也是一列项目，列表项目使用数字进行标记。

有序列表始于 <ol> 标签。每个列表项始于 <li> 标签。

```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```

浏览器显示如下：

1. Coffee
2. Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

------

### 定义列表

自定义列表不仅仅是一列项目，而是项目及其注释的组合。

自定义列表以 <dl> 标签开始。每个自定义列表项以 <dt> 开始。每个自定义列表项的定义以 <dd> 开始。

```html
<dl>
<dt>Coffee</dt>
<dd>Black hot drink</dd>
<dt>Milk</dt>
<dd>White cold drink</dd>
</dl>
```

浏览器显示如下：

- Coffee

  Black hot drink

- Milk

  White cold drink

定义列表的列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

------

### 列表标签

![](https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-26-20.png)

------

## HTML块

### HTML <div> div 和 <span> span

------

**可以通过 <div> 和 <span> 将 HTML 元素组合起来。**

------

### HTML 块元素

大多数 HTML 元素被定义为块级元素或内联元素。

编者注：“块级元素”译为 block level element，“内联元素”译为 inline element。

块级元素在浏览器显示时，通常会以新行来开始（和结束）。

例子：<h1>, <p>, <ul>, <table>

------

### HTML 内联元素

内联元素在显示时通常不会以新行开始。

例子：<b>, <td>, <a>, <img>

------

### HTML <span> 元素

HTML <span> 元素是内联元素，可用作文本的容器。

<span> 元素也没有特定的含义。

当与 CSS 一同使用时，<span> 元素可用于为部分文本设置样式属性。

------

### HTML 分组标签

![](https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-05_20-30-33.png)

------

## HTML表单

### HTML表单详解

------

**HTML 表单用于搜集不同类型的用户输入。**

------

在HTML中，一个完整的表单通常由表单控件（也称为表单元素）、提示信息和表单域3个部分构成。表单目的是为了收集用户信息。

![图片](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)**表单控件：**

>  包含了具体的表单功能项，如单行文本输入框、密码输入框、复选框、提交按钮、重置按钮等。

**提示信息：**

>  一个表单中通常还需要包含一些说明性的文字，提示用户进行填写和操作。

**表单域：** 

>  它相当于一个容器，用来容纳所有的表单控件和提示信息，可以通过他定义处理表单数据所用程序的url地址，以及数据提交到服务器的方法。如果不定义表单域，表单中的数据就无法传送到后台服务器。

------

### **「1. input 控件」**

```html
<input type="属性值" value="你好">
```

- input 输入的意思
- <input />标签为单标签
- type属性设置不同的属性值用来指定不同的控件类型
- 除了type属性还有别的属性

**常用属性：**

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_17-53-13.png" style="zoom:80%;" />

```html
用户名: <input type="text" /> 
密  码：<input type="password" />
```

------

#### **value属性**

- value 默认的文本值。有些表单想刚打开页面就默认显示几个文字，就可以通过这个value 来设置。

```html
用户名:<input type="text"  name="username" value="请输入用户名"> 
```

#### **name属性**

- name表单的名字， 这样，后台可以通过这个name属性找到这个表单。 页面中的表单很多，name主要作用就是用于区别不同的表单。

- - name属性后面的值，是我们自己定义的。
  - radio  如果是一组，我们必须给他们命名相同的名字 name  这样就可以多个选其中的一个啦
  - name属性，我们现在用的较少，但是，当我们学ajax 和后台的时候，是必须的。

```
<input type="radio" name="sex"  />男
<input type="radio" name="sex" />女
```

#### **checked属性**

- 表示默认选中状态。 较常见于 单选按钮和复选按钮。

```
性    别:
<input type="radio" name="sex" value="男" checked="checked" />男
<input type="radio" name="sex" value="女" />女 
```

------

#### **提交按钮**

*<input type="submit">* 定义用于向*表单处理程序*（form-handler）*提交*表单的按钮。

表单处理程序通常是包含用来处理输入数据的脚本的服务器页面。

表单处理程序在表单的 *action* 属性中指定：

##### 实例

```html
<form action="action_page.php">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```

#### **input 属性小结**

| 属性    | 说明     | 作用                                                   |
| :------ | :------- | ------------------------------------------------------ |
| type    | 表单类型 | 用来指定不同的控件类型                                 |
| value   | 表单值   | 表单里面默认显示的文本                                 |
| name    | 表单名字 | 页面中的表单很多，name主要作用就是用于区别不同的表单。 |
| checked | 默认选中 | 表示那个单选或者复选按钮一开始就被选中了               |

------

### **「2.  label标签」**

- label 标签为 input 元素定义标注（标签）。
- label标签主要目的是为了提高用户体验。为用户提高最优秀的服务。

**作用：**用于绑定一个表单元素, 当点击label标签的时候, 被绑定的表单元素就会获得输入焦点。

**如何绑定元素呢**

- 第一种用法就是用label标签直接包含input表单， 适合单个表单选择
- 第二种用法 for 属性规定 label 与哪个表单元素绑定(通过id)。

```html
  第一种
  <label> 用户名： 
    <input type="radio" name="usename" value="请输入用户名">   
  </label>
  
  第二种
  <label for="sex">男</label>
  <input type="radio" name="sex"  id="sex">
```

------



### **「3.  textarea控件(文本域)」**

- 通过textarea控件可以轻松地创建多行文本输入框.
- cols="每行中的字符数" rows="显示的行数"  我们实际开发不用

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_18-46-04.png" style="zoom:80%;" />

```html
  <textarea >
    文本内容
  </textarea>
```

#### **文本框和文本域区别**

| 表单              |  名称  |       区别       |                  默认值显示 |             用于场景 |
| :---------------- | :----: | :--------------: | --------------------------: | -------------------: |
| input type="text" | 文本框 | 只能显示一行文本 | 单标签，通过value显示默认值 | 用户名、昵称、密码等 |
| textarea          | 文本域 | 可以显示多行文本 |  双标签，默认值写到标签中间 |               留言板 |

------

**「4.  select下拉列表」**

- ### 如果有多个选项让用户选择，为了节约空间，我们可以使用select控件定义下拉列表。

- 在option 中定义selected =" selected "时，当前项即为默认选中项。

- 我们实际开发会用的比较少

![图片](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)

```html
<select>
  
  <option>选项1</option>
  <option>选项2</option>
  <option>选项3</option>
  ...
</select>
```

------

### HTML 表单属性详解

------

#### Action 属性

`action` 属性定义提交表单时要执行的操作。

通常，当用户单击“提交”按钮时，表单数据将发送到服务器上的文件中。

在下面的例子中，表单数据被发送到名为 "page.php" 的文件。该文件包含处理表单数据的服务器端脚本：

##### 实例

提交后，将表单数据发送到 "page.php"：

```html
<form action="page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="Bill"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Gates"><br><br>
  <input type="submit" value="Submit">
</form>
```

------

#### Target 属性

`target` 属性规定提交表单后在何处显示响应。

`target` 属性可设置以下值之一：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-03-06.png" style="zoom:80%;" />

默认值为 `_self`，这意味着响应将在当前窗口中打开。

##### 实例

此处，提交的结果将在新的浏览器标签中打开：

```html
<form action="page.php" target="_blank">
```

------

#### Method 属性

method 属性指定提交表单数据时要使用的 HTTP 方法。

表单数据可以作为 URL 变量（使用 `method="get"`）或作为 HTTP post 事务（使用 `method="post"`）发送。

提交表单数据时，默认的 HTTP 方法是 GET。

##### 实例

此例在提交表单数据时使用 GET 方法：

```html
<form action="/action_page.php" method="get">
```

##### 实例

此例在提交表单数据时使用 POST 方法：

```html
<form action="/action_page.php" method="post">
```

##### 关于 GET 的注意事项：

- 以名称/值对的形式将表单数据追加到 URL
- 永远不要使用 GET 发送敏感数据！（提交的表单数据在 URL 中可见！）
- URL 的长度受到限制（2048 个字符）
- 对于用户希望将结果添加为书签的表单提交很有用
- GET 适用于非安全数据，例如 Google 中的查询字符串

##### 关于 POST 的注意事项：

- 将表单数据附加在 HTTP 请求的正文中（不在 URL 中显示提交的表单数据）
- POST 没有大小限制，可用于发送大量数据。
- 带有 POST 的表单提交无法添加书签

**提示：**如果表单数据包含敏感信息或个人信息，请务必使用 POST！

------

#### Autocomplete 属性

`autocomplete` 属性规定表单是否应打开自动完成功能。

启用自动完成功能后，浏览器会根据用户之前输入的值自动填写值。

##### 实例

启用自动填写的表单：

```html
<form action="/action_page.php" autocomplete="on">
```

------

#### Novalidate 属性

`novalidate` 属性是一个布尔属性。

如果已设置，它规定提交时不应验证表单数据。

##### 实例

未设置 novalidate 属性的表单：

```html
<form action="/action_page.php" novalidate>
```

------

#### 所有 <form>  form属性的列表

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-10-14.png"  />

------

### HTML 表单元素详解

#### <input>  input元素

最重要的表单元素是 *<input>* 元素。

<input> 元素根据不同的 *type* 属性，可以变化为多种形态。

------

#### <select>  select元素（下拉列表）

*<select>* 元素定义*下拉列表*：

##### 实例

```html
<select name="cars">
<option value="volvo">Volvo</option>
<option value="saab">Saab</option>
<option value="fiat">Fiat</option>
<option value="audi">Audi</option>
</select>
```

*<option>* 元素定义待选择的选项。

列表通常会把首个选项显示为被选选项。

您能够通过添加 selected 属性来定义预定义选项。

##### 实例

```html
<option value="fiat" selected>Fiat</option>
```

------

#### <textarea>  textarea元素

*<textarea>* 元素定义多行输入字段（*文本域*）：

##### 实例

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

以上 HTML 代码在浏览器中显示为：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-31-01.png" style="zoom:80%;" />

------

#### <button> button 元素

*<button>* 元素定义可点击的*按钮*：

##### 实例

```html
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

以上 HTML 代码在浏览器中显示为：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-34-58.png" style="zoom:80%;" />

------

#### HTML5 表单元素

HTML5 增加了如下表单元素：

- <datalist>
- <keygen>
- <output>

**注释：**默认地，浏览器不会显示未知元素。新元素不会破坏您的页面。

------

#### HTML5 <datalist>  detalist元素

*<datalist>* 元素为 <input> 元素规定预定义选项列表。

用户会在他们输入数据时看到预定义选项的下拉列表。

<input> 元素的 *list* 属性必须引用 <datalist> 元素的 *id* 属性。

##### 实例

通过 <datalist> 设置预定义值的 <input> 元素：

```html
<form action="page.php">
<input list="browsers">
<datalist id="browsers">
   <option value="Internet Explorer">
   <option value="Firefox">
   <option value="Chrome">
   <option value="Opera">
   <option value="Safari">
</datalist> 
</form>
```

------

### HTML 输入类型

#### 输入类型：text

*<input type="text">* 定义供*文本输入*的单行输入字段：

##### 实例

```html
<form>
 First name:<br>
<input type="text" name="firstname">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-38-30.png" style="zoom:80%;" />

------

#### 输入类型：password

*<input type="password">* 定义*密码字段*：

##### 实例

```html
<form>
 User name:<br>
<input type="text" name="username">
<br>
 User password:<br>
<input type="password" name="psw">
</form> 
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-40-22.png" style="zoom:80%;" />

**注释：**password 字段中的字符会被做掩码处理（显示为星号或实心圆）。

------

#### 输入类型：submit

*<input type="submit">* 定义*提交*表单数据至*表单处理程序*的按钮。

表单处理程序（form-handler）通常是包含处理输入数据的脚本的服务器页面。

在表单的 action 属性中规定表单处理程序（form-handler）：

##### 实例

```html
<form action="action_page.php">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-41-44.png" style="zoom:80%;" />

------

#### Input Type: radio

<input type="radio"> 定义单选按钮。

Radio buttons let a user select ONLY ONE of a limited number of choices:

##### 实例

```html
<form>
<input type="radio" name="sex" value="male" checked>Male
<br>
<input type="radio" name="sex" value="female">Female
</form> 
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-44-38.png" style="zoom:80%;" />

------

#### Input Type: checkbox

<input type="checkbox"> 定义复选框。

复选框允许用户在有限数量的选项中选择零个或多个选项。

##### 实例

```html
<form>
<input type="checkbox" name="vehicle" value="Bike">I have a bike
<br>
<input type="checkbox" name="vehicle" value="Car">I have a car 
</form> 
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-46-06.png" style="zoom:80%;" />

------

#### HTML5 输入类型

HTML5 增加了多个新的输入类型：

- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

**注释：**老式 web 浏览器不支持的输入类型，会被视为输入类型 text。

------

##### 输入类型：number

*<input type="number">* 用于应该包含数字值的输入字段。

您能够对数字做出限制。

根据浏览器支持，限制可应用到输入字段。

##### 实例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>表单控件之HTML5新属性</title>
</head>
<body>
    <p>
        根据浏览器支持：<br>
        数值约束会应用到输入字段中。
        </p>
        
        <form action="/demo/demo_form.asp">
          数量（1 到 5 之间）：
          <input type="number" name="quantity" min="1" max="5">
          <input type="submit">
        </form>
        
        <p><b>注释：</b>IE9 及早期版本不支持 type="number"。</p>
</body>
</html>
```

------

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-50-30.png" style="zoom:80%;" />

------

##### 输入限制

这里列出了一些常用的输入限制（其中一些是 HTML5 中新增的）：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-51-49.png"  />

------

##### 输入类型：date

*<input type="date">* 用于应该包含日期的输入字段。

根据浏览器支持，日期选择器会出现输入字段中。

##### 实例

```html
<form>
  Birthday:
  <input type="date" name="bday">
</form>
```

以上 HTML 代码在浏览器中看上去是这样的：

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_19-54-40.png" style="zoom:80%;" />

------

##### 输入类型：color

*<input type="color">* 用于应该包含颜色的输入字段。

根据浏览器支持，颜色选择器会出现输入字段中。

##### 实例

```html
<form>
  Select your favorite color:
  <input type="color" name="favcolor">
</form>
```

------

##### 输入类型：range

*<input type="range">* 用于应该包含一定范围内的值的输入字段。

根据浏览器支持，输入字段能够显示为滑块控件。

##### 实例

```html
<!DOCTYPE html>
<html>
<body>

<p>
根据浏览器支持：<br>
输入类型 "range" 可显示为滑动控件。
</p>

<form action="/demo/demo_form.asp" method="get">
  Points:
  <input type="range" name="points" min="0" max="10">
  <input type="submit">
</form>

<p><b>注释：</b>IE9 及早期版本不支持 type="range"。</p>

</body>
</html>

```

<img src="C:\Users\lemon\Pictures\截图5（2022）\Snipaste_2022-02-06_19-59-07.png" style="zoom:80%;" />

------

##### 输入类型：month

*<input type="month">* 允许用户选择月份和年份。

根据浏览器支持，日期选择器会出现输入字段中。

##### 实例

```html
<form>
  Birthday (month and year):
  <input type="month" name="bdaymonth">
</form>
```

------

##### 输入类型：week

*<input type="week">* 允许用户选择周和年。

根据浏览器支持，日期选择器会出现输入字段中。

##### 实例

```html
<form>
  Select a week:
  <input type="week" name="week_year">
</form>
```

------

##### 输入类型：time

*<input type="time">* 允许用户选择时间（无时区）。

根据浏览器支持，时间选择器会出现输入字段中。

##### 实例

```html
<form>
  Select a time:
  <input type="time" name="usr_time">
</form>
```

------

##### 输入类型：datetime

*<input type="datetime">* 允许用户选择日期和时间（有时区）。

根据浏览器支持，日期选择器会出现输入字段中。

##### 实例

```html
<form>
  Birthday (date and time):
  <input type="datetime" name="bdaytime">
</form>
```

------

##### 输入类型：datetime-local

*<input type="datetime-local">* 允许用户选择日期和时间（无时区）。

根据浏览器支持，日期选择器会出现输入字段中。

##### 实例

```html
<form>
  Birthday (date and time):
  <input type="datetime-local" name="bdaytime">
</form>
```

------

##### 输入类型：email

*<input type="email">* 用于应该包含电子邮件地址的输入字段。

根据浏览器支持，能够在被提交时自动对电子邮件地址进行验证。

某些智能手机会识别 email 类型，并在键盘增加 ".com" 以匹配电子邮件输入。

##### 实例

```html
<form>
  E-mail:
  <input type="email" name="email">
</form>
```

------

##### 输入类型：search

*<input type="search">* 用于搜索字段（搜索字段的表现类似常规文本字段）。

##### 实例

```html
<form>
  Search Google:
  <input type="search" name="googlesearch">
</form>
```

------

##### 输入类型：tel

*<input type="tel">* 用于应该包含电话号码的输入字段。

目前只有 Safari 8 支持 tel 类型。

##### 实例

```html
<form>
  Telephone:
  <input type="tel" name="usrtel">
</form>
```

------

##### 输入类型：url

*<input type="url">* 用于应该包含 URL 地址的输入字段。

根据浏览器支持，在提交时能够自动验证 url 字段。

某些智能手机识别 url 类型，并向键盘添加 ".com" 以匹配 url 输入。

##### 实例

```html
<form>
  Add your homepage:
  <input type="url" name="homepage">
</form>
```

------

### form表单域

- 收集的用户信息怎么传递给服务器？

- - 通过form表单域

  目的：

- - 在HTML中，form标签被用于定义表单域，以实现用户信息的收集和传递，form中的所有内容都会被提交给服务器。

```html
<form action="url地址" method="提交方式" name="表单名称">
  各种表单控件
</form>
```

#### **常用属性：**

<img src="https://cdn.jsdelivr.net/gh/gaoziman/bed/img/Snipaste_2022-02-06_18-53-49.png" style="zoom:80%;" />

- 每个表单都应该有自己表单域。

| 属性   | 属性值   | 作用                                               |
| :----- | :------- | :------------------------------------------------- |
| action | url地址  | 用于指定接收并处理表单数据的服务器程序的url地址。  |
| method | get/post | 用于设置表单数据的提交方式，其取值为get或post。    |
| name   | 名称     | 用于指定表单的名称，以区分同一个页面中的多个表单。 |



### **GET 和 POST 的区别**

- GET在浏览器回退时是无害的，而POST会再次提交请求。
- GET请求会被浏览器主动cache，而POST不会，除非手动设置。
- GET请求只能进行url编码，而POST支持多种编码方式。
- GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。
- GET请求大小一般是(1024字节)，http协议并没有限制，而与服务器，操作系统有关，POST理论上来说没有大小限制，http协议规范也没有进行大小限制，但实际上post所能传递的数据量根据取决于服务器的设置和内存大小。
- 对参数的数据类型，GET只接受ASCII字符，而POST没有限制。
- GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。

#### **团队约定：**

- 元素属性值使用双引号语法
- 元素属性值可以写上的都写上

```html
推荐
<input type="text" /> 
<input type="radio" name="name" checked="checked" />
```

------











### 从输入url到页面展示发生了什么(面试)

> 作者：Twinkle_
> 链接：https://juejin.im/post/6869279683230629896
> 来源：掘金

##### **浏览器的多进程架构**

从浏览器输入 URL 到页面渲染的整个过程都是由 浏览器架构中的各个进程之间的配合完成。

1. 浏览器主进程: 管理子进程、提供服务功能
2. 渲染进程：将HTML、CSS、JS渲染成界面，js引擎v8和排版引擎Blink就在上面，他会为每一个tab页面创建一个渲染进程
3. GPU进程：本来是负责处理3Dcss的，后来慢慢的UI界面也交给GPU来绘制
4. 网络进程：就是负责网络请求，网络资源加载的进程
5. 插件进程：负责插件的运行的，因为插件很容易崩溃，把它放到独立的进程里不要让它影响别人

**浏览器的多进程架构**

从用户输入信息到页面展示的不同阶段，是不同的进程在发挥作用，示意图如下：![图片](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)从图中可以看出，整个过程是需要各个进程之间相互配合完成的，过程大致可以描述为：

1. 用户输入url,处理输入信息，主进程开始导航，交给网络进程干活
2. 网络进程发起网络请求，其中有可能会发生重定向
3. 服务器响应URL之后，主进程就要通知渲染进程，你要开始干活了
4. 渲染进程准备好了，要想渲染进程提交数据，这个时间叫做提交文档
5. 渲染进程接受到数据，完成页面渲染。

**具体过程**

1. 输入url

用户输入url，处理输入信息：如果为非url结构的字符串，交给浏览器默认引擎去搜索改字符串；若为url结构的字符串，浏览器主进程会交给 网络进程 ,开始干活。
2.1 查找浏览器缓存网络进程会先看看是否存在本地缓存，如果有就直接返回资源给浏览器进程，无则下一步 DNS-> IP -> TCP2.2 DNS解析网络进程拿到url后，先会进行DNS域名解析得到IP地址。如果请求协议是HTTPS，那么还需要建立TLS连接。
2.2 建立TCP连接，三次握手接下来就是利用IP地址和服务器建立TCP连接。连接建立之后，向服务器发送请求。
服务器响应服务器收到请求信息后，会根据请求信息生成响应行、响应头、响应体，并发给网络进程。网络进程接受了响应信息之后，就开始解析响应头的内容。网络进程解析响应行和响应头信息的过程：
3.1 重定向如果响应行状态码为301（永久重定向）和302（临时），那么说明需要重定向到其他url。这时候网络进程会从响应头中的Location字段里读取重定向的地址，并重新发起网络请求。
3.2 响应数据处理导航会通过请求头的Content-type字段判断响应体数据的类型。浏览器通过这个来决定如何显示响应体的内容。比如：若为application/octet-stream，则会按照下载类型来处理这个请求，导航结束。若为text/html，这就告诉浏览器服务器返回的是html格式，浏览器会通知渲染进程，你要干活了。准备渲染进程默认情况，每个页面一个渲染进程。但若处于同一站点（同根域名+协议），那么渲染进程就会复用。提交文档渲染进程准备好后，浏览器进程发出“提交文档的消息”，渲染进程接受了消息之后，会跟网络进程简历传输数据的管道。等数据传输完成了，渲染进程会告诉浏览器进程，确认文档提交，这时候浏览器会更新页面，安全状态，url，前进后退的历史。到这里导航结束，进入渲染阶段。
注：当浏览器刚开始加载一个地址之后，标签页上的图标便进入了加载状态。但此时图中页面显示的依然是之前打开的页面内容，并没立即替换为百度首页的页面。因为需要等待提交文档阶段，页面内容才会被替换。前端HTML基础面试题iframe有哪些缺点？iframe是一种框架，也是一种很常见的网页嵌入方式。**「iframe的优点」**iframe能够原封不动的把嵌入的网页展现出来。如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。**「iframe的缺点」**会产生很多页面，不容易管理。iframe框架结构有时会让人感到迷惑，如果框架个数多的话，可能会出现上下、左右滚动条，会分散访问者的注意力，用户体验度差。代码复杂，无法被一些搜索引擎索引到，这一点很关键，现在的搜索引擎爬虫还不能很好的处理iframe中的内容，所以使用iframe会不利于搜索引擎优化。很多的移动设备（PDA 手机）无法完全显示框架，设备兼容性差。iframe框架页面会增加服务器的http请求，对于大型网站是不可取的。现在基本上都是用Ajax来代替iframe，所以iframe已经渐渐的退出了前端开发。label的作用是什么？是怎么用的？例子1: 点击" 用户名:" 就可以定位光标到输入框`<form><label for="myid "> 用户名:</label><input type="text" id="myid" /></form> `例子2: 点击" 用户名:" 或按键alt+1, 都可以定位光标到输入框`<form>  <label for="myid" accesskey="1"> 用户名:</label>  <input type="text" id="myid" tabindex="1" /></form> `**for 属性**功能：表示Label 标签要绑定的HTML 元素，你点击这个标签的时候，所绑定的元素将获取焦点。**acesskey 属性**
功能：表示访问Label 标签所绑定的元素的热键，当您按下热键，所绑定的元素将获取焦点。
局限性：accessKey 属性所设置的快捷键不能与浏览器的快捷键冲突，否则将优先激活浏览器的快捷键。HTML5的form如何关闭自动完成功能？  HTML的输入框可以拥有自动完成的功能，当你往输入框输入内容的时候，浏览器会从你以前的同名输入框的历史记录中查找出类似的内容并列在输入框下面，这样就不用全部输入进去了，直接选择列表中的项目就可以了。
  但有时候我们希望关闭输入框的自动完成功能，例如当用户输入内容的时候，我们希望使用AJAX技术从数据库搜索并列举而不是在用户的历史记录中搜索。**关闭输入框的自动完成功能有3种方法：**在IE的Internet选项菜单里的内容--自动完成里面设置设置form的autocomplete为"on"或者"off"来开启或者关闭自动完成功能设置输入框的autocomplete为"on"或者"off"来开启或者关闭该输入框的自动完成功能将 HTML5 看作成开放的网络平台**「什么是 HTML5 的基本构件（building block）？」**语义 - 提供更准确地描述内容。连接 - 提供新的方式与服务器通信。离线和存储 - 允许网页在本地存储数据并有效地离线运行。多媒体 - 在 Open Web 中，视频和音频被视为一等公民（first-class citizens）。2D/3D 图形和特效 - 提供更多种演示选项。性能和集成 - 提供更快的访问速度和性能更好的计算机硬件。设备访问 - 允许使用各种输入、输出设备。外观 - 可以开发丰富的主题。浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？  在浏览器的html头部加上manifest属性，如果是第一次访问浏览器会根据manifest的内容进行下载存储离线内容，如果已经访问过则从离线存储中进行加载，然后在比对服务器如果有新内容在更新离线存储
  离线的情况下，浏览器就直接使用离线存储的资源。浏览器的渲染过程？
  `1、将获取的html解析成dom树 2、处理css，构成层叠样式表模型CSSOM3、将dom树和CSSOM合并为渲染树4、根据CSSOM将渲染树的节点布局计算5、将渲染树节点样式绘制到页面上 // 注意在渲染的过程中是自上而下渲染，js会阻塞页面的渲染，优先等js执行完成如果在渲染的过程中改变了样式，会造成回流需要重新渲染`link和@import的区别？`1、从属关系区别：link属于html标签，而@import是css提供的。2、加载顺序区别：页面被加载时，link会同时被加载，而@import引用的css会等到页面被加载完再加载。3、兼容性区别：import只在IE5以上才能识别，而link是html标签，无兼容问题。4、dom可操作性区别：可以通过JS 操作 DOM ，插入link标签来改变样式；由于 DOM 方法是基于文档的，无法使用@import的方式插入样式5、权重区别：如果已经存在相同样式，@import引入的这个样式将被该 CSS 文件本身的样式层叠掉，表现出link方式的样式权重高于@import的权重这样的直观效果。（简而言之，link和@import，谁写在后面，谁的样式就被应用，后面的样式覆盖前面的样式。） `src与href的区别？`1、href 是指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，用于超链接。2、src是指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将`

