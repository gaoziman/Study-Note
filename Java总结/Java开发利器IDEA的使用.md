# IntelliJ IDEA工具的使用

## 1. 常见的Java集成开发工具

- Eclipse
  - IBM团队研发的一个开源的非常好用的集成开发环境。寓意：吞并Sun公司。不过Sun最终被Oracle公司收购了。目前仍然有一部分团队在使用该工具。
- NetBeans
  - Sun公司在2000年创立的开放源代码供开发人员和客户社区的家园，旨在构建世界级的Java IDE。在国内使用较少。
- IntelliJ IDEA
  - JetBrains公司研发。JetBrains是捷克的一家软件开发公司。该公司位于捷克的布拉格，并在俄罗斯的圣彼得堡及美国麻州波士顿都设有办公室，该公司最为人所熟悉的产品是Java编程语言开发撰写时所用的集成开发环境：IntelliJ IDEA。
  - IDEA在业界被公认为最好的Java开发工具，尤其在智能代码助手、代码自动提示、重构、JavaEE支持、各类版本工具（git、svn）、JUnit、CVS整合、代码分析、创新的GUI设计等方面的功能可以说是超常的。所以IDEA是国内目前使用最为广泛的Java开发工具。
- 其它...

## 2. 安装IntelliJ IDEA工具

- 新建Empty Project

## 3.激活IDEA工具

## 4. 在Project下新建Module模块

- File菜单 -> new -> Module...

## 5. 在src下新建软件包package

- 在src目录上右键 -> new -> package
- 点击右上角“设置”图标，选中“Flatten Packages”表示以并列方式显示所有的包。取消选中则表示以树形结构显示包。

## 6. 在package下新建class

- 在package下新建类，先选中package，然后在package上点击右键-> new -> class

## 7. 在class中编写main方法并运行

- psvm 直接生成main方法
- sout 直接生成System.out.println()语句
- 运行
  - 在有main方法的程序文件中右键-> Run...
  - 或者点击绿色箭头
- ctrl + y 删除一行
- 不要敲额外的空格，破坏IDEA自动生成的缩进格式
- 在IDEA中编写的源码在哪儿？在IDEA中编译生成的class字节码在哪儿？

## 8. IDEA编译报错和不报错时的区别

- 报错时的表现是出现红色字体、出现红色下划线（波浪线），右上角提示错误的数量。
- 没有报错时不会出现红色字体、不会出现红色下划线，右上角一般是一个绿色对号。

## 9. IDEA最基本的提示功能

- 在IDEA中只要敲一个字母就会自动提示一次。
- 方法的提示图标是m，并且方法的参数类型、含义，以及方法的名称，方法的返回值类型等都会提示。
- 属性的提示图标是f

## 10. 在IDEA当中的注释

- ctrl + / 注释或者取消注释（单行）
- ctrl + shift + / 注释或者取消注释（多行）
- /** 回车，这样会自动生成javadoc注释

## 11. IDEA中运行程序的其他方式以及警告

- 可以找到包下要运行的类，类上面右键-> run
- 可以在右上角“小锤子”后面选中你要执行的程序，点击右侧绿色箭头
- 可以在Run窗口中点击绿色箭头
- 在程序右上角出现的“黄色叹号”是程序的警告。

## 12. 设置字体的大小、字体样式、行间距

- File -> settings -> font

## 13. alt + 数字键

- 隐藏或展示IDEA的视图窗口
- alt + 1 是Project窗口
- alt + 4 是Run窗口
- alt + 5 是Debug窗口

## 14. 运行的快捷键

- ctrl + shift + F10

## 15. 代码窗口最大化和最小化快捷键

- ctrl + shift + F12

## 16. 多个tab页切换快捷键

- alt + 右/左方向键

## 17. 在IDEA当中新建的统一快捷键

- alt + insert
- 退出的统一快捷键：esc

## 18. 自动生成代码

- 在类体的任意位置：alt + insert，选中你要生成的
- constructor：生成构造方法
- setter and getter：生成set和get方法
- toString：生成toString方法
- equals：生成equals方法

## 19. 重写父类的方法

- ctrl + o

## 20. 自动纠错

- alt + 回车

## 21. 代码格式化

- ctrl + alt + L

## 22. 自动生成for循环

- fori

## 23. 自动生成判断引用是否为null的代码

- ifn

## 24. 复制一行 

- ctrl + d

## 25. 一次编辑多行

- 按住alt键，别松手，光标往下拉。

## 26. 撤销和重做

- ctrl + z 撤销
- ctrl + shift + z 重做（解决掉搜狗的快捷键冲突）

## 27. IDEA强大的搜索功能

- 敲两次shift，输入你要搜索的资源。

## 28. 快速查看某个类当中的成员

- ctrl + F12

## 29. 优化import

- ctrl + alt + o

## 30. 提示方法的参数

- ctrl + p

## 31. 自动生成变量

- ctrl + alt + v

## 32. IDEA工具会自动保存你的代码

- ctrl + s 是不需要的。

## 33. IDEA的批量替换功能

- ctrl + r

## 34. IDEA替换所有文件中的某个内容

- ctrl + shift + r

## 35. 回到上一个/下一个代码的操作位置

- ctrl + alt + 左/右方向

## 36. 打开IDEA的系统设置

- ctrl + alt + s

## 37. 直接跳转到实现类具体的方法上

- ctrl + alt + b

## 38. 查看源代码

- 按住ctrl键不松手，然后鼠标移动到要查看的元素下面，单击。

## 39. 查看类的继承结构

- ctrl + h

## 40. 查看方法的调用层次结构

- ctrl + alt + h

