# Markdown语法

## 欢迎使用Markdown编辑器

你好！ 这是你第一次使用 **Markdown编辑器** 所展示的欢迎页。如果你想学习如何使用Markdown编辑器, 可以仔细阅读这篇文章，了解一下Markdown的基本语法知识。

### 首先介绍一下Markdown一些基本的快捷键

1. 撤销：<kbd>Ctrl/Command</kbd> + <kbd>Z</kbd>
2. 重做：<kbd>Ctrl/Command</kbd> + <kbd>Y</kbd>
3. 加粗：<kbd>Ctrl/Command</kbd> + <kbd>B</kbd>
4. 斜体：<kbd>Ctrl/Command</kbd> + <kbd>I</kbd>
5. 标题：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd>
6. 无序列表：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>U</kbd>
7. 有序列表：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>O</kbd>
8. 检查列表：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>C</kbd>
9. 插入代码：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>K</kbd>
10. 插入链接：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>L</kbd>
11. 插入图片：<kbd>Ctrl/Command</kbd> + <kbd>Shift</kbd> + <kbd>G</kbd>
12. 查找：<kbd>Ctrl/Command</kbd> + <kbd>F</kbd>
13. 替换：<kbd>Ctrl/Command</kbd> + <kbd>G</kbd>

ctrl+z 撤销

ctrl +y 取消撤销

ctrl + s 保存

ctrl + B 加粗

ctrl + I 斜体

ctrl +U 下划线

ctrl + shift + ` (esc下面那个)单行代码

ctrl +shift + K 代码块

alt + shift + 5 删除线

ctrl + k 超链接

ctrl + \ 清除样式

ctrl + / 注释

ctrl + c 复制

ctrl + v 粘贴

ctrl + x 剪切

ctrl + shift + C 复制为markdown

ctrl+ shift + v 粘贴为纯文本

ctrl + 0~6 六级标题一一对应

ctrl + T 插入表格

ctrl + shift +q 引用

ctrl + [ 减少缩进

ctrl + ]增加缩进

ctrl + shift + [ 有序列表

ctrl + shift + ]无序列表

提升标题等级ctrl + =

降低标题等级 ctrl + -

显示隐藏侧边栏 ctrl + shift + L
————————————————
版权声明：本文为CSDN博主「haust_允谦」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qiangqiang103/article/details/115281231

## 合理的创建标题有助于目录的生成

直接输入1次<kbd>#</kbd>，并按下<kbd>space</kbd>后，将生成1级标题。
输入2次<kbd>#</kbd>，并按下<kbd>space</kbd>后，将生成2级标题。
以此类推，我们支持6级标题。有助于使用`TOC`语法后生成一个完美的目录。

## 如何改变文本的样式

强调文本* _强调文本_

**加粗文本** __加粗文本__

==标记文本==

~~删除文本~~

> 引用文本

H~2~O is是液体。

2^10^ 运算结果是 1024.

## 插入图片与链接

![java](C:\Users\lemon\Pictures\Saved Pictures\j.png)这是小尺寸图片

<img src="C:\Users\lemon\Pictures\Saved Pictures\QQ图片20210804210620.jpg" alt="[小姐姐]" style="zoom: 33%;" />这是一些可以带尺寸的图片

当然为了用户小伙伴们的操作便捷，也是可以从桌面对图片进行拖拽。

## 如何插入一段漂亮的代码

在tab键上面有一个键 带着点跟波浪号，按三次点以后（前提是英文状态下） 然后再点击空格就可以了，最后选着自己要插入的不同代码，如java，c ，c++ c# python php等

```java
System.out.println("hello,world");
```

## 生成一个适合你的列表

### 有序列表

1. 项目一
2. 项目二
3. 项目三

### 无序列表

- 项目
- 项目
- 项目

## 创建一个表格

一个简单的表格就是这么创建的

| 电脑 |      | 手机 |
| ---- | ---- | ---- |
| 5000 |      | 4000 |
|      |      |      |
|      |      |      |

<span style='color:orange'>创建一个表格</span>

<span style='color:blue'>语法问题</span>

# 更改颜色字体的方法

## 方法一：<span style='color:文字颜色;background:背景颜色;font-size:文字大小;font-family:字体;'></span>



## 方法二：改html代码

按照这个模板，改字体的style属性即可。

示例：

style="color:red"

style="color:maroon"

style="color:fuchsia"

style="color:brown"

style="color:blue"

style="color:aqua"

style="color:green"

style="color:orange"

style="color:purple"

style="color:white;background:black;"

style="background:yellow"

style="background:red"

style="background:orange"

style="color:white;background:green"

style="color:white;background:blue"


![图片](C:\Users\lemon\Desktop\1.png)

## 方法三：使用内联公式（较为复杂）

## 菜单栏
**文件: alt+F**
**编辑: alt+E**
**段落: alt+P**
**格式: alt+O**
**视图: alt+V**
**主题: alt+T**
文件
**帮助: alt+H**
**新建: ctrl+N**
**新建窗口: ctrt+shift+N**
**打开: ctrl+O**
**快速打开: ctrl+P**
**保存: ctrl+S**
**另存为: ctrl+shift+S**
**偏好: ctrl+,**
**关闭: ctrl+W**
段落
**标题: ctrl+1/2/3/4/5/6**
**段落: ctrl+O**
**增大标题级别: ctrl+=**
**减少标题级别: ctrl±**
**表格: ctrl+T**
**代码块: ctrl+shift+K**
**公式块: ctrl+shift+M**
**引用: ctrl+shift+Q**
**有序列表: ctrl+shift+[**
**无序列表: ctrl+shift+]**
**增加缩进: ctrl+]**
**减少缩进: ctrl+[**
格式
**加粗: ctrl+B**
**斜体: ctrl+I**
**下划线: ctrl+U**
**代码: ctrl+shift+`**
**删除线: alt+shift+5**
**超链接: ctrl+K**
**图像: ctrl+shift+I**
**清除样式: ctrl+**
视图
**显示隐藏侧边栏: ctrl+shift+L**
大**纲视图: ctrl+shift+1**
**文档列表视图: ctrl+shift+2**
**文件树视图: ctrl+shift+3**
**源代码模式: ctrl+/**
**专注模式: F8**
**打字机模式: F9**
**切换全屏: F11**
**实际大小: ctrl+shift+0**
**放大: ctrl+shift+=**
**缩小: ctrl+shift±**
**应用内窗口切换: ctrl+tab**
**打开DevTools: shift+F12**
