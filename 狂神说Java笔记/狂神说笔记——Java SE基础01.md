# [狂神说笔记——Java SE基础01](https://www.cnblogs.com/gh110/p/15153669.html)

# 计算机预科

## 1.打开CMD的方式

1. 开始 + 系统 + 命令提示符。
2. Win + R 输入 CMD 打开控制台 (推荐使用)。
3. 在任意文件夹下，按住Shift键 + 鼠标右键打开命令行窗口。
4. 在资源管理器的地址栏前加上 CMD 路径。

## 2.管理员身份运行方式

- 选择以管理员方式运行。

## 3.常见的Dos命令

1. 盘符切换

   

   ```c
   C:\Users\subei>D
   'D' 不是内部或外部命令，也不是可运行的程序
   或批处理文件。
   
   C:\Users\subei>D:
   
   D:\>C:
   
   C:\Users\subei>F:
   
   F:\>
   ```

2. 查看当前盘符目录下的全部目录：dir

   

   ```c
   F:\>dir
    驱动器 F 中的卷是 工作台
    卷的序列号是 1714-20F6
   
    F:\ 的目录
   
   2021/05/17  16:15    <DIR>          BaiduNetdiskDownload
   2021/05/15  19:50    <DIR>          CloudMusic
   2021/05/14  21:19    <DIR>          Dev-Cpp
   2021/05/14  16:56    <DIR>          DTL8Folder
   2021/05/14  22:35    <DIR>          HBuilderX
   2021/05/14  22:36    <DIR>          java
   2021/05/14  17:00    <DIR>          MyDrivers
   2021/05/14  22:47    <DIR>          Notepad++
   2021/05/14  22:29    <DIR>          Sublime Text 3
   2021/05/14  18:56    <DIR>          Typora
   2021/05/17  17:53    <DIR>          VCW
   2021/05/14  21:25    <DIR>          VS2017
   2021/05/14  21:47    <DIR>          Windows Kits
                  0 个文件              0 字节
                 13 个目录 663,783,088,128 可用字节
   
   F:\>E:
   
   E:\>dir
    驱动器 E 中的卷是 数据
    卷的序列号是 3F12-1129
   
    E:\ 的目录
   
   2020/06/04  07:47       610,571,366 AI教程超级合辑.zip
   2021/05/14  13:44    <DIR>          java
   2021/05/14  21:47    <DIR>          NUT
   2021/05/14  13:45    <DIR>          Office Tool
   2021/05/05  15:18        69,730,999 Office-Tool-with-runtime-v8.1.zip
   2021/05/11  17:26    <DIR>          作业
   2021/05/14  23:15    <DIR>          工具
   2021/05/14  13:38    <DIR>          论文
   2020/10/21  21:58         1,000,218 狂神说Java全栈学习路线.jpg
                  3 个文件    681,302,583 字节
                  6 个目录 605,834,113,024 可用字节
   
   E:\>
   ```

3. 切换目录：cd change directory

   

   ```c
   E:\>cd /d d:
   
   d:\>cd /d d:\leven
   
   d:\LEVEN>cd ..
   
   d:\>
   ```

4. 返回上一级：cd …

5. 清理屏幕： cls

6. 退出终端：exit

7. 查看电脑IP信息：ipconfig

8. 打开计算机：calc

9. 打开画图：mspaint

10. 打开记事本：notepad

11. ping命令：ping 网址

12. 文件操作

    

    ```c
    C:\Users\subei\Desktop>md test
    
    C:\Users\subei\Desktop>cd test
    
    C:\Users\subei\Desktop\test>cd>a.txt
    
    C:\Users\subei\Desktop\test>
    ```

13. 删除文件

    

    ```c
    C:\Users\subei\Desktop\test>del a.txt
    
    C:\Users\subei\Desktop\test>cd ..
    
    C:\Users\subei\Desktop>rd test
    
    C:\Users\subei\Desktop>
    ```

# 基础

## 1.Java简介

- java的特性和优势

  - 简单性
  - 面向对象
  - 可移植性
  - 高性能
  - 分布式
  - 动态性
  - 多线程
  - 安全性
  - 健壮性

- Java的三大版本

  - JavaSE：标准版（桌面程序，控制台开发……）
  - JavaME：嵌入式开发（手机、小家电……）
  - JavaEE：E企业级开发（Web端、服务器开发……）

- Java安装与卸载开发环境

  - 卸载JDK

    - 删除Java安装目录；
    - 删除JAVA_HOME；
    - 删除path下关于java的目录；
    - java -version验证。

  - 下载路径：[地址](https://www.oracle.com/java/technologies/javase-downloads.html)

  - 安装教程：

    传送门

    - 官网下载JDK8(选择JDK8,比较稳定)；
    - 安装JDK，步骤如上传送门。

## 2.Hello World

- Hello World

  1. 随便新建一个文件夹，存放代码。

  2. 新建一个Java文件

     1. 文件后缀名为.java
     2. Hello.java
     3. 注意：系统可能没有文件的后缀名，需手动打开显示文件后缀名。

  3. 编写代码

     

     ```java
     public class Hello {
     
     	public static void main(String[] args) {
     		System.out.println("Hello World!Java!");
     	}
     
     }
     ```

  4. 编译javac.java文件，会生成一个class文件！

  5. 运行class文件，java class文件。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213557810.png#pic_center)

- 可能会遇到的问题
  1. 每个单词的大小不能出现问题，Java是大小写敏感的；
  2. 尽量使用英文；
  3. 文件名和类名必须保证一致，并且首字母大写；
  4. 符号使用的了中文。
- Java运行机制
  - 编译型
  - 解释型
- IDEA2020.2安装
  - [传送门](https://www.jb51.net/article/194557.htm)
- Java中的注释有三种：
  - 单行注释：只能注释一行文字
  - 多行注释：可以注释一段文字
  - 文档注释

```java
/**
 * @author subeiLY
 * @create 2021-05-23 21:21
 */
public class Hello {
    // 单行注释

    /*
    多行注释
     */

    /**
     * 文档注释
     * @param args
     */
    public static void main(String[] args) {
        // 输出一个Hello World!
        System.out.println("Hello World!");
    }

    /**
     *    有趣的代码注释                            _(\_/)
     *                              ,((((^`\
     *                             ((((  (6 \
     *                           ,((((( ,    \
     *       ,,,_              ,(((((  /"._  ,`,
     *      ((((\\ ,...       ,((((   /    `-.-'
     *      )))  ;'    `"'"'""((((   (
     *     (((  /            (((      \
     *      )) |                      |
     *     ((  |        .       '     |
     *     ))  \     _ '      `t   ,.')
     *     (   |   y;- -,-""'"-.\   \/
     *     )   / ./  ) /         `\  \
     *        |./   ( (           / /'
     *        ||     \\          //'|
     *        ||      \\       _//'||
     *        ||       ))     |_/  ||
     *        \_\     |_/          ||
     *        `'"                  \_\
     *                             `'"
     *
     */
}
```

## 3.标识符与关键字

- 标识符
  - 所有的标识符都应该以字母(A-Z 或者 a-z)，美元符($)，或者下划线(_)开始；
  - 首字符之后可以是字母（A-Z 或者 a-z）美元符（$）、下划线（）或数字的任何字符组合；
  - 不能使用关键字作为变量名或方法名；
  - 标识符是大小写敏感的；
  - 可以使用中文命名，但是一般不建议这样去使用，也不建议使用拼音。

```java
/**
 * @author subeiLY
 * @create 2021-05-24 18:36
 */
public class Demo01 {
    public static void main(String[] args) {

        String Ahello = "subeiLY";
        String hello = "subeiLY";
        String $hello = "subeiLY";
        String _hello = "subeiLY";

        String _vvhh = "subeiLY";
        String 王者荣耀 = "subeiLY";
        
    }
}
```

- 关键字

| abstract  | boolean    | break        | byte       | case     |
| --------- | ---------- | ------------ | ---------- | -------- |
| catch     | char       | const        | class      | continue |
| default   | do         | double       | else       | extends  |
| final     | finally    | float        | for        | goto     |
| if        | implements | import       | instanceof | int      |
| interface | long       | native       | new        | package  |
| private   | protected  | public       | return     | short    |
| static    | strictfp   | super        | switch     | this     |
| throw     | throws     | transient    | try        | void     |
| volatile  | while      | synchronized |            |          |

## 4.数据类型

- 强类型语言
  - 要求变量的使用要严格符合规定，所有变量都必须先定义后才能使用。
- 弱类型语言
- 数据类型基本分类
  - 基本类型
    - 数值类型
      - 整数类型
        - byte占1字节，范围：-128 - 127
        - short占2字节，范围： **-2^15** - **2^15-1**
        - int占4字节，范围： **-2^31** - **2^31 - 1**
        - long占8字节，范围： **-2^63** - **2^63-1**
      - 浮点类型
        - float占4字节
        - double占8字节
      - 字符类型：char占2字节
    - boolean类型：占1位其值只有tue和fase两个。
  - 引用类型
    - 类
    - 接口
    - 数组

```java
/**
 * @author subeiLY
 * @create 2021-05-24 19:06
 */
public class Demo02 {
    public static void main(String[] args) {
        // 八大基本数据类型
        
        // 整数
        int num1 = 10;  // 最常用
        byte num2 = 20;
        short num3 = 30;
        long num4 = 40L; // Long类型要在数字后面加L

        // 小数：浮点数
        float num5 = 50.1F; // float类型要在数字后面加F
        double num6 = 3.1415926534546246455;

        // 字符类型
        char name = 'A';

        // 字符串，String不是关键字，类
        String names = "subeiLY";

        // 布尔值
        boolean flag = true;
        boolean flag2 = false;
    }
}
```

- 什么是字节
  - 位（bit）：是计算机内部数据储存的最小单位，11001100是一个八位二进制数。
  - 字节（byte）：是计算机中数据处理的基本单位，习惯上用大写B来表示，1B（byte字节）=8bit（位）。
  - 字符：是指计算机中使用的字母、数字、字和符号。
    - 1bit表示1位
    - 1Byte表示一个字节1B=8b
    - 1024B=1KB
    - 1024KB=1M
    - 1024M=1G

> 数据类型扩展及面试题

```java
/**
 * @author subeiLY
 * @create 2021-05-25 9:17
 */
public class Demo03 {
    public static void main(String[] args) {
        // 整数拓展：    进制      二进制0b   十进制     八进制0    十六进制0x

        int i=10;
        int i2 = 010;   // 八进制0
        int i3 = 0x10;  // 十六进制0x

        System.out.println(i);  // 10
        System.out.println(i2); // 8
        System.out.println(i3); // 16

        System.out.println("-------------------------------------");
        //************************************************
        // 浮点数拓展
        // BigDecimal   数据工具类
        // float 有限     离散      舍入误差    大约  接近但不等于
        // 最好完全使用浮点数进行比较

        float f = 0.1f; // 0.1
        double d = 1.0/10;  // 0.1

        System.out.println(f==d);   // false

        float d1 = 2425444564215654564f;
        float d2 = d1 + 1;

        System.out.println(d1==d2); // true

        System.out.println("-------------------------------------");
        //************************************************
        // 字符拓展
        char c1 = 'a';
        char c2 = '中';

        System.out.println(c1);
        System.out.println((int)c1);    // 强制转换

        System.out.println(c2);
        System.out.println((int)c2);    // 强制转换

        // 所有字符的本质还是数字
        // 编码 Unicode   2字节    0 - 65536   Excel

        char c3 = '\u0061';

        System.out.println(c3); // a

        // 转义字符
        // \t   制表符
        // \n   换行
        // ......

        System.out.println("hello\tworld!");
        System.out.println("hello\nworld!");

        System.out.println("-------------------------------------");

        //
        String sa = new String("hello world");
        String sb = new String("hello world");
        System.out.println(sa==sb);     // false

        String sc = "hello world";
        String sd = "hello world";
        System.out.println(sc==sd);     // true

        // 布尔值扩展
        boolean flag = true;
        
        if(flag==true){}    // 新手
        if(flag){}      // 老油条
        
        // 代码要精简易读
    }
}
```

## 5.类型转换

- 由于Java是强类型语言，所以要进行有些运算的时候的，需要用到类型转换。

  

  ```java
  低 ------------------------------------------------> 高
  byte -> short -> char -> int -> long -> float -> double
  ```

- 运算中，不同类型的数据先转化为同一类型，然后进行运算。

```java
/**
 * @author subeiLY
 * @create 2021-05-25 9:45
 */
public class Demo04 {
    public static void main(String[] args) {
        int i = 128;
        byte b = (byte)i;   // 内存溢出
        double b1 = i;

        // 强制转换     (类型)变量名     高--低
        // 自动转换     低--高

        System.out.println(i);
        System.out.println(b);
        System.out.println(b1);

        /*
        注意点：
        1.不能对布尔类型转换
        2.不能将对象类型转换为不相干的类型
        3.在把高容量转换到低容量时，强制转换
        4.转换的时候可能存在内存溢出，或者精度问题！
         */

        System.out.println("++++++++++++++++++++++++++++++++++++");

        System.out.println((int)123.7);
        System.out.println((int)-45.89f);

        System.out.println("=======================");
        char a = 'a';
        int c = a+1;

        System.out.println(c);  // 98
        System.out.println((char)c);    // b

    }
}
```

- 常见问题

```java
/**
 * @author subeiLY
 * @create 2021-05-25 9:56
 */
public class Demo05 {
    public static void main(String[] args) {
        // 操作比较大时，注意溢出
        // JDK7新特性，数字之间可以用下划线分割
        int money = 10_0000_0000;
        System.out.println(money);

        int years = 20;
        int total = money*years;    //  -1474836480  计算时溢出
        System.out.println(total);

        long total2 = money*years;
        System.out.println(total2);    // 默认是int，转换之前已经存在问题了!!!

        long total3 = money*(long)years;
        System.out.println(total3);     // 20000000000

    }
}
```

## 6.变量与常量

- 变量：可以变化的量。
- Java是一种强类型语言，每个变量都必须声明其类型。
- Java变量是程序中最基本的存储单元，其要素包括变量名，变量类型和作用域。
- 每个变量都有类型，类型可以是基本类型，也可以是引用类型；
- 变量名必须是合法的标识符；
- 变量声明是一条完整的语句，因此每一个声明都必须以分号结束。

```java
/**
 * @author subeiLY
 * @create 2021-05-25 10:46
 */
public class Demo06 {

    static int allClicks = 0;   // 类变量
    String str = "hello world"; // 实例变量

    public void method(){
        int i = 0;  // 局部变量
    }

    public static void main(String[] args) {
        // int a,b,c;
        // int a=1,b=2,c=3;
        String name = "wahaha";
        char x = 'X';
        double pi = 3.14;

    }
}
/**
 * @author subeiLY
 * @create 2021-05-25 10:52
 */
public class Demo07 {
    // 类变量 static
    static double salary = 2500;

    // 属性：变量

    // 实例变量:从属于对象：实例变量：从属于对象；如果不自行初始化，这个类型的默认值 0 0.0
    // 布尔值：默认是 faLse
    // 除了基本类型，其余的都是null
    String name;
    int age;

    // main 方法
    public static void main(String[] args) {
        // 局部变量：必须声明和初始化值
        int i = 10;

        System.out.println(i);

        // 变量类型 变量名字 = new Demo08();
        Demo07 demo07 = new Demo07();
        System.out.println(demo07.age);
        System.out.println(demo07.name);

        // 类变量 static
        System.out.println(salary);

    }

    // 其他方法
    public void add(int i){
        System.out.println(i);
    }
}
```

- 常量（ Constant）：初始化（ initialize）后不能再改变值！不会变动的值；
- 所谓常量可以理解成一种特殊的变量，它的值被设定后，在程序运行过程中不允许被改变。
- 常量名一般使用大写字符。

```java
/**
 * @author subeiLY
 * @create 2021-05-25 14:45
 */
public class Demo08 {
    
    // 修饰符，不存在先后顺序
    static final double PI = 3.14;

    public static void main(String[] args) {
        System.out.println(PI);
    }
}
```

- 变量的命名规范
  - 所有变量、方法、类名：见名知意；
  - 类成员变量：首字母小和驼峰原则：monthSalary；
  - 局部变量：首字母小写和驼峰原则；
  - 常量：大写字母和下划线：MAX_VALUE；
  - 类名：首字母大写和驼峰原则：Man, GoodMan；
  - 方法名：首字母小写和驼峰原则：run()，runRun()。

## 7.基本运算符

> Java语言支持如下运算符：

- 算术运算符：+，-，*，/，%，++，–
- 赋值运算符: =
- 关系运算符：>，≤，>=，<=，==，!=， instanceof
- 逻辑运算符：&&，‖，!
- 位运算符：&，|，A，~，>>，<<，>>>（了解！！！）
- 条件运算符: ？：
- 扩展赋值运算符：+=，-=，*=，/=

```java
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 15:14
 */
public class Demo01 {
    public static void main(String[] args) {
        // 二元运算符
        int a = 10;
        int b = 20;
        int c = 25;
        int d = 25;

        System.out.println(a+b);
        System.out.println(a-b);
        System.out.println(a*b);
        System.out.println(a/b);
        System.out.println(a/(double)b);
    }
}
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 16:03
 */
public class Demo02 {
    public static void main(String[] args) {
        long a = 123123123123123L;
        int b = 123;
        short c = 10;
        byte d = 8;

        System.out.println(a+b+c+d);
        System.out.println(b+c+d);
        System.out.println(c+d);
    }
}
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 16:03
 */
public class Demo02 {
    public static void main(String[] args) {
        long a = 123123123123123L;
        int b = 123;
        short c = 10;
        byte d = 8;

        System.out.println(a+b+c+d);
        System.out.println(b+c+d);
        System.out.println(c+d);
        System.out.println((double)c+d);
    }
}
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 18:03
 */
public class Demo03 {
    public static void main(String[] args) {
        // 关系运算符返回的结果

        int a = 10;
        int b = 20;
        int c = 21;

        System.out.println(c%a);    // c / a 的余数

        System.out.println(a>b);
        System.out.println(a<b);
        System.out.println(a==b);
        System.out.println(a!=b);
    }
}
```

## 8.自增自减运算符、初识Math类

```java
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 20:00
 */
public class Demo04 {
    public static void main(String[] args) {
        // ++ -- 自增，自减  一元运算符
        int a = 3;

        int b = a++;    // 执行完这一行代码后，先给b赋值，再自增
        System.out.println(a);
        int c = ++a;    // 执行完这一行代码前，先自增，再给c赋值

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);

        // 幂运算 2^3
        double pow = Math.pow(2,3);
        System.out.println(pow);

    }
}
```

## 9.逻辑运算符、位运算符

```java
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-25 20:10
 */
public class Demo05 {
    // 逻辑运算符
    public static void main(String[] args) {
        // 与(and)   或(or)   非(取反)
        boolean a = true;
        boolean b = false;

        System.out.println("a && b:" + (a && b));   // 逻辑与：两个变量都为真，结果才为true
        System.out.println("a || b:" + (a || b));   // 逻辑或：两个变量有一个为真，则结果才为true
        System.out.println("!(a && b):" + !(a && b));   // 取反：如果是真，则变为假；如果是假，则变为真

        // 短路运算
        int c = 5;
        boolean d = (c<4)&&(c++<4);
        System.out.println(d);
        System.out.println(c);

    }
}
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-26 9:11
 */
public class Demo06 {
    public static void main(String[] args) {
        /*
        A = 0011 1100
        B = 0000 1101
----------------------------------
        A&B = 0000 1100
        A|B = 0011 1101
        A^B = 0011 0001
        ~B = 1111 0010

        2*8 = 16
        << *2
        >> /2

         */

        System.out.println(2<<3);
    }
}
```

## 10.三元运算符

```java
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-26 9:39
 */
public class Demo07 {
    public static void main(String[] args) {
        int a = 10;
        int b = 20;

        a += b; //  a = a+b
        a -= b; //  a = a-b

        System.out.println(a);

        // 字符串连接
        System.out.println(""+a+b);

        System.out.println(a+b+"");
        
    }
}
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-26 9:43
 */
public class Demo08 {
    public static void main(String[] args) {
        // 三元运算符
        // x ？ y : z
        // 如果x==true,则结果为y，否则结果为z

        int score = 80;
        String type = score < 60 ? "不及格" : "及格";
        System.out.println(type);
        
    }
}
```

## 11.包机制

- 为了更好地组织类，Java提供了包机制，用于区别类名的命名空间。
- 包语句的语法格式为：

```java
package pkg1[.pkg2[.pkg3……]];
```

- 一般利用公司域名倒置作为包名；
- 为了能够使用某一个包的成员，我们需要在Java程序中明确导入该包。使用" import"语句可完成此功能。

```java
import package1[.package2……].(classname | *);
```

## 12.JavaDoc

- javadoc命令是用来生成自己API文档的。
- 参数信息
  - @ author作者名
  - @ version版本号
  - @ since指明需要最早使用的jdk版本
  - @ paran参数名
  - @ return返回值情况
  - @ throws异常抛出情况

```java
package github.demo01;

/**
 * @author subeiLY
 * @create 2021-05-26 10:20
 * @version 1.0
 * @since 1.8
 */
public class Doc {
    
    String name;

    /**
     * @author 
     * @param name
     * @return
     * @throws Exception
     */
    public String test(String name) throws Exception{
        return name;
    }
}
javadoc -encoding UTF-8 -charset UTF-8 Doc.java
```

# 流程控制

## 1.用户交互 Scanner

- 之前我们学的基本语法中我们并没有实现程序和人的交互，但是Java给我们提供了这样一个工具类，我们可以获取用户的输入。 java. util. Scanner是Java5的新特征，我们可以通过Scanner类来获取用户的输入。

- 基本语法

  

  ```java
  Scanner s = new Scanner(System.in);
  ```

- 通过 Scanner类的next()与 nextLine()方法获取输入的字符串，在读取前我们一般需要使用 hasNext()与 hasNextLine()判断是否还有输入的数据。

```java
package github.liuc;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 10:42
 */
public class Demo01 {
    public static void main(String[] args) {
        // 创建一个扫描器对象，用于接收键盘数据
        Scanner scanner = new Scanner(System.in);

        System.out.println("使用next方法接收:");

        // 判断用户有没有输入字符串
        if(scanner.hasNext()){
            String str = scanner.next();
            System.out.println("输入的内容为:" + str);
        }

        // 凡是属于IO流的类如果不关闭会一直占用资源
        scanner.close();
    }
}
package github.liuc;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 10:48
 */
public class Demo02 {
    public static void main(String[] args) {
        // 从键盘接收数据
        Scanner scanner = new Scanner(System.in);

        System.out.println("使用nextLine方式接收:");

        // 判断是否还有输入
        if(scanner.hasNextLine()){
            String str = scanner.nextLine();
            System.out.println("输出的内容为:" + str);
        }

        scanner.close();
    }
}
```

- next()：
  - 1、一定要读取到有效字符后才可以结束输入。
  - 2、对输入有效字符之前遇到的空白，next()方法会自动将其去掉。
  - 3、只有输入有效字符后才将其后面输入的空白作为分隔符或者结束符。
  - 4、next()不能得到带有空格的字符串。
- nextLine()：
  - 1、以 Enter为结束符也就是说 nextLine()方法返回的是输入回车之前的所有字符。
  - 2、可以获得空白。

```java
package github.liuc;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 10:58
 */
public class Demo04 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 从键盘接收数据
        int i = 0;
        float f = 0.0f;

        System.out.println("请输入整数:");

        // 如果……那么……
        if(scanner.hasNextInt()){
            i = scanner.nextInt();
            System.out.println("整数数据:" + i);
        }else{
            System.out.println("输入的不是整数数据！");
        }

        System.out.println("请输入小数:");

        // 如果……那么……
        if(scanner.hasNextFloat()){
            f = scanner.nextFloat();
            System.out.println("小数数据:" + f);
        }else{
            System.out.println("输入的不是小数数据！");
        }

        scanner.close();
    }
}
package github.liuc;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 14:17
 */
public class Demo05 {
    public static void main(String[] args) {
        // 求输入的数字的总和及平均数
        Scanner scanner = new Scanner(System.in);

        // 和
        double sum = 0;
        // 计算输入了多少个数字
        int m = 0;

        // 通过循环判断是否输入，并统计求和
        while(scanner.hasNextDouble()){
            double x = scanner.nextDouble();
            System.out.println("你输入了第" + m + "个数据，当前结果为sum=" + sum);
            m = m +1;
            sum = sum + x;
        }

        System.out.println(m + "个数的和为:" + sum);
        System.out.println(m + "个数的平均数是:" + (sum/m));

        scanner.close();
    }
}
```

## 2.顺序结构

- JAVA的基本结构就是顺序结构，除非特别指明，否则就按照顺序一句一句执行。
- 顺序结构是最简单的算法结构。
- 语句与语句之间，框与框之间是按从上到下的顺序进行的，它是由若干个依次执行的处理步骤组成的，它是任何一个算法都离不开的一种基本算法结构。

```java
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 14:27
 */
public class SXDemo01 {
    public static void main(String[] args) {
        System.out.println("hello1");
        System.out.println("hello2");
        System.out.println("hello3");
        System.out.println("hello4");
        System.out.println("hello5");
        System.out.println("hello6");
        System.out.println("hello7");
        System.out.println("hello8");
    }
}
```

## 3.选择结构

- if单选择结构

  - 我们很多时候需要去判断一个东西是否可行，然后我们才去执行，这样一个过程在程序中用if语句来表示。

  

  ```java
  if(布尔表达式){
      // 如果布尔表达式为true将执行的语句
  }
  ```

  

  ```java
  package github.struct;
  
  import java.util.Scanner;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 14:30
   */
  public class IFDemo01 {
      public static void main(String[] args) {
          Scanner scanner = new Scanner(System.in);
  
          System.out.println("请输入内容:");
          String s = scanner.nextLine();
  
          // equals：判断字符串是否相等
          if(s.equals("Hello")){
              System.out.println(s);
          }
  
          System.out.println("End");
  
          scanner.close();
      }
  }
  ```

- if双选择结构

  

  ```java
  if(布尔表达式){
      // 如果布尔表达式为true
  }else{
      // 如果布尔表达式值为false
  }
  ```

  

  ```java
  package github.struct;
  
  import java.util.Scanner;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 14:36
   */
  public class IFDemo02 {
      public static void main(String[] args) {
          // 考试分数大于60就是及格，小于60则为不及格
          Scanner scanner = new Scanner(System.in);
  
          System.out.println("请输入成绩:");
          int score = scanner.nextInt();
  
          if(score>60){
              System.out.println("及格");
          }else {
              System.out.println("不及格");
          }
  
          scanner.close();
      }
  }
  ```

- if多选择结构

```java
if(布尔表达式1){
    // 如果布尔表达式1为true执行代码
}else if(布尔表达式2){
    // 如果布尔表达式2为true执行代码
}else if(布尔表达式3){
    // 如果布尔表达式3为true执行代码
}else{
    // 如果以上布尔表达式值都不为true执行代码
}
package github.struct;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 14:41
 */
public class IFDemo03 {
    public static void main(String[] args) {
        // 考试分数大于60就是及格，小于60则为不及格
        Scanner scanner = new Scanner(System.in);

        System.out.println("请输入成绩:");
        int score = scanner.nextInt();

        if(score==100){
            System.out.println("恭喜满分！");
        }else if(score<100 && score >=90){
            System.out.println("A级");
        }else if(score<90 && score >=80){
            System.out.println("B级");
        }else if(score<80 && score >=70){
            System.out.println("C级");
        }else if(score<70 && score >=60){
            System.out.println("D级");
        }else if(score<60 && score >=0){
            System.out.println("不及格");
        }else{
            System.out.println("成绩不合法");
        }

        scanner.close();
    }
}
```

- 嵌套的f结构

  

  ```java
  if(布尔表达式1){
      // 如果布尔表达式1为true执行代码
  	if(布尔表达式2){
      	// 如果布尔表达式2为true执行代码
  	}
  }
  ```

- switch多选择结构

  - 多选择结构还有一个实现方式就是 switch case语句。
  - switch case语句判断一个变量与一系列值中某个值是否相等，每个值称为一个分支。

```java
package github.struct;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-26 14:48
 */
public class IFDemo04 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //
        char grade = 'K';
        switch (grade){
            case 'A':
                System.out.println("优秀");
                break;
            case 'B':
                System.out.println("良好");
                break;
            case 'C':
                System.out.println("及格");
                break;
            case 'D':
                System.out.println("再接再厉");
                break;
            case 'E':
                System.out.println("挂科");
                break;
            default:
                System.out.println("成绩错误！！！");
        }

        scanner.close();
    }
}
```

## 4.循环结构

- while循环

  

  ```java
  while(布尔表达式){
      // 循环内容
  }
  ```

  - 只要布尔表达式为true，循环就会一直执行下去。
  - 我们大多数情况是会让循环停止下来的，我们需要一个让表达式失效的方式来结束循环。
  - 少部分情况需要循环一直执行，比如服务器的请求响应监听等。
  - 循环条件一直为true就会造成无限循环【死循环】，我们正常的业务编程中应该尽量避免死循环。会影响程序性能或者造成程序卡死奔溃！

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:06
   */
  public class WileDemo01 {
      public static void main(String[] args) {
          // 输出1~100
          int i = 0;
  
          while(i<100){
              i++;
              System.out.println(i);
          }
      }
  }
  ```

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:07
   */
  public class WileDemo02 {
      public static void main(String[] args) {
          // 死循环
          while(true){
              // 等待客户链接
              // 定时检查
          }
      }
  }
  ```

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:09
   */
  public class WhileDemo03 {
      public static void main(String[] args) {
          // 计算1+2+3+...+100=？
  
          int i = 0;
          int sum = 0;
  
          while(i<=100){
              sum = sum + i;
              i++;
          }
          
          System.out.println(sum);
      }
  }
  ```

- do……while循环

  

  ```java
  do{
      // 代码语句
  }while(布尔表达式);
  ```

  - do……while循环和 while循环相似，不同的是，do…while循环至少会执行一次。

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:15
   */
  public class DoWhileDemo01 {
      public static void main(String[] args) {
          // 计算1+2+3+...+100=？
  
          int i = 0;
          int sum = 0;
  
          do{
              sum = sum + i;
              i++;
          }while(i<=100);
  
          System.out.println(sum);
      }
  }
  ```

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:16
   */
  public class DoWhileDemo02 {
      public static void main(String[] args) {
          int a = 0;
          while(a<0){
              System.out.println(a);
              a++;
          }
          System.out.println("==================");
          do{
              System.out.println(a);
              a++;
          }while(a<0);
      }
  }
  ```

> - While和do- While的区别：
> - while先判断后执行。 do……while是先执行后判断！
> - Do……while总是保证循环体会被至少执行一次！这是他们的主要差别。

- for循环

  - for循环语句是支持迭代的一种通用结构，是最有效、最灵活的循环结构。
  - for循环执行的次数是在执行前就确定的。语法格式如下：

  

  ```java
  for(初始化;布尔表达式;更新){
      // 代码语句
  }
  ```

  

  ```java
  package github.struct;
  
  /**
   * @author subeiLY
   * @create 2021-05-26 15:19
   */
  public class ForDemo01 {
      public static void main(String[] args) {
          int a = 1;  // 初始化条件
          while(a<=100){  // 条件判断
              System.out.println(a);  // 循环体
              a+=2;   // 迭代
          }
  
          System.out.println("while循环结束!");
  
          // 初始化 条件判断 迭代
          for(int i=1;i<=100;i++){
              System.out.println(i);
          }
  
          System.out.println("for循环结束!");
      }
  }
  ```

  - 关于for循环有以下几点说明：
    - 最先执行初始化步骤。可以声明一种类型，但可初始化一个或多个循环控制变量，也可以是空语句。
    - 然后，检测布尔表达式的值。如果为true，循环体被执行。如果为false，循环终止，开始执行循环体后面的语句。
    - 执行一次循环后，更新循环控制变量（迭代因子控制循环变量的增减）。
    - 再次检测布尔表达式，执行上面的过程。

```java
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:25
 */
public class ForDemo02 {
    public static void main(String[] args) {
        // 计算0到100之间的奇数和偶数的和

        int oddSum = 0;
        int evenSum = 0;

        for(int i = 0;i<=100;i++){
            if(i%2!=0){
                oddSum+=i;
            }else{
                evenSum+=i;
            }
        }

        System.out.println("奇数的和:" + oddSum);
        System.out.println("偶数的和:" + evenSum);
    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:28
 */
public class ForDemo03 {
    public static void main(String[] args) {
        // 用whiLe或for循环输出1-1000之间能被5整除的数，并且每行输出3个
//        for (int i = 0; i < 1000; i++) {
//            if(i%5==0){
//                System.out.print(i + "\t");
//            }
//            if(i%(5*3)==0){ // 每行
//                System.out.println();
//                // System.out.print("\n");
//            }
//
//            /*
//            println : 输出完会换行
//            print : 输出完不会换行
//             */
//        }

        int i = 0;
        while(i<1000){
            if(i%5==0){
                System.out.print(i + "\t");
            }
            if(i%(5*3)==0){ // 每行
                System.out.println();
            }
            i++;
        }

    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:34
 */
public class ForDemo04 {
    public static void main(String[] args) {
        // 打印9*9乘法表
        for(int i = 1;i <= 9;i++){
            for(int j = 1;j <= i;j++){
                System.out.print(i + "*" + j + "=" + i*j + "\t");
            }
            System.out.println();
        }
    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:42
 */
public class ForDemo05 {
    public static void main(String[] args) {
        int[] numbers = {10,20,30,40,50};   // 定义一个数组

        for(int i = 0;i<5;i++){
            System.out.println(numbers[i]);
        }

        System.out.println("========================");

        // 遍历数组的元素
        for(int x:numbers){
            System.out.println(x);
        }

    }
}
```

## 5.break& continue

- break在任何循环语句的主体部分，均可用 break控制循环的流程。 break用于强行退出循环，不执行循环中剩余的语句。（ break语句也在 switch语句中使用）。
- continue语句用在循环语句体中，用于终止某次循环过程，即跳过循环体中尚未执行的语句，接着进行下一次是否执行循环的判定。
- 关于goto关键字
  - goto关键字很早就在程序设计语言中出现。尽管goto仍是Java的一个保留字，但并未在语言中得到正式使用；Java没有goto。然而，在 breaki和 continue这两个关键字的身上，我们仍然能看出一些goto的影子—带标签的 break和continue。
  - “标签”是指后面跟一个冒号的标识符，例如：label；
  - 对Java来说唯一用到标签的地方是在循环语句之前。而在循环之前设置标签的唯一理由是：我们希望在其中嵌套另一个循环，由于 break和 continue关键字通常只中断当前循环，但若随同标签使用，它们就会中断到存在标签的地方。

```java
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:47
 */
public class BreakDemo01 {
    public static void main(String[] args) {
        int i = 0;
        while(i<100){
            i++;
            System.out.println(i);
            if(i==30){
                break;
            }
        }

        System.out.println("123");
    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:49
 */
public class ContinueDemo {
    public static void main(String[] args) {
        int i = 0;
        while(i<100){
            i++;
            if(i%10==0){
                System.out.println();
                continue;
            }
            System.out.println(i);
        }
    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:55
 */
public class LabelDemo {
    public static void main(String[] args) {
        // 打印101~150之间的所有质数
        // 质数是指在大的自然数中，除1和它本身以外不再有其他因数的自然数。

        int count = 0;

        outer:for(int i = 101;i<150;i++){
            for(int j = 2;j<i/2;j++){
                if(i%j==0){
                    continue outer;
                }
            }
            System.out.print(i + " ");
        }

    }
}
package github.struct;

/**
 * @author subeiLY
 * @create 2021-05-26 15:59
 */
public class TestDemo01 {
    // 打印三角形
    public static void main(String[] args) {
        for(int i=1;i<=5;i++){
            for(int j = 5;j>=i;j--){
                System.out.print(" ");
            }
            for(int j = 1;j<=i;j++){
                System.out.print("*");
            }
            for(int j = 1;j<i;j++){
                System.out.print("*");
            }
            System.out.println();
        }
    }
}


/*
输出效果：
     *
    ***
   *****
  *******
 *********
 
 */
```

# 方法

## 1.何谓方法

- Java方法是语句的集合，它们在一起执行一个功能。
  - 方法是解决一类问题的步骤的有序组合；
  - 方法包含于类或对象中；
  - 方法在程序中被创建，在其他地方被引用。
- 设计方法的原则：方法的本意是功能块，就是实现某个功能的语句块的集合。我们设计方法的时候，最好保持方法的原子性，就是一个方法只完成1个功能，这样利于我们后期的扩展。

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 9:28
 */
public class Demo01 {

    // main方法
    public static void main(String[] args) {
        int sum = add(1, 2);
        System.out.println(sum);
    }

    // 加法
    public static int add(int a,int b){
        return a+b;
    }
}
```

## 2.方法的定义及调用

- Java的方法类似于其它语言的函数，是一段用来完成特定功能的代码片段，一般情况下，定义一个方法包含以下语法：

- 方法包含一个方法头和一个方法体。下面是一个方法的所有部分：

  - **修饰符**：修饰符，这是可选的，告诉编译器如何调用该方法。定义了该方法的访问类型。

  - **返回值类型**：方法可能会返回值。 returnValueType是方法返回值的数据类型。有些方法执行所需的操作，但没有返回值。在这种情况下， returnValueType是关键字void。

  - **方法名**：是方法的实际名称。方法名和参数表共同构成方法签名。

  - 参数类型

    ：参数像是一个占位符。当方法被调用时，传递值给参数。这个值被称为实参或变量。参数列表是指方法的参数类型、顺序和参数的个数。参数是可选的，方法可以不包含任何参数。

    - 形式参数：在方法被调用时用于接收外界输入的数据。
    - 实参：调用方法时实际传给方法的数据。

  - **方法体**：方法体包含具体的语句，定义该方法的功能。

  

  ```java
  修饰符 返回值类型 方法名(参数类型 参数名){
      ...
      方法体
      ...
      return 返回值;
  }
  ```

- 调用方法：对象名.方法名（实参列表）

- Java支持两种调用方法的方式，根据方法是否返回值来选择，当方法返回一个值的时候，方法调用通常被当做一个值。例如：

```java
int larger = max(30,40);
```

- 如果方法返回值是void，方法调用一定是一条语句。

```java
System.out.println("Hello,subeiLY!");
```

- 案例

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 9:46
 */
public class Demo02 {

    public static void main(String[] args) {
        int max = max(10, 20);
        System.out.println(max);
    }

    // 比大小
    public static int max(int num1,int num2){
        int result = 0;

        if(num1==num2){
            System.out.println("num1==num2");
            return 0;   // 终止方法
        }

        if(num1>num2){
            result = num1;
        } else {
            result = num2;
        }

        return result;
    }
}
```

> 课后作业：值传递和引用传递

- 方法可以修改**传递引用所对应的**变量值，而**不能修改传递值调用**所对应的变量值，这句话相当重要，这是按值调用与引用调用的根本区别，以下为分析：
- 按值调用(call by value)表示方法接受的时调用者**提供的值**。

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 9:58
 */
public class HomeWork01 {
    private static int x = 10;

    public static void updataeValue(int value){
        value = 3 * value;
        System.out.println("value的值:" + value);
    }

    public static void main(String[] args) {
        System.out.println("调用前的值:" + x);
        updataeValue(x);
        System.out.println("调用后的值:" + x);
    }

}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213459924.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/2021062121345155.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

**分析**：

- 1）value被初始化为x值的一个拷贝（也就是10）
- 2）value被乘以3后等于30，但注意此时x的值仍为10！
- 3）这个方法结束后，参数变量value不再使用，被回收。

> **结论：**当传递方法参数类型为基本数据类型（数字以及布尔值）时，一个方法是不可能修改一个基本数据类型的参数。

- 按引用调用(call by reference)
- 按引用调用则表示方法接收的是**调用者提供的变量地址**(如果是C语言的话来说就是指针啦，当然java并没有指针的概念)
- 当然java中除了基本数据类型还有**引用数据类型**，也就是**对象引用**，那么对于这种数据类型又是怎么样的情况呢？我们还是一样先来看一个例子：
  先声明一个User对象类型：

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 10:07
 */
public class User {
    private String name;
    private int age;

    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

- 执行class

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 10:09
 */
public class HomeWork02 {

    public static void updateUser(User student){
        student.setName("subeiLY");
        student.setAge(22);
    }

    public static void main(String[] args) {
        User user = new User("SUBEI",20);
        System.out.println("调用user前的值:" + user.getName() + "," + user.getAge());
        updateUser(user);
        System.out.println("调用user后的值:" + user.getName() + "," + user.getAge());
    }
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213437761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 分析一下这个过程：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213428721.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

**分析**：

- 1）student变量被初始化为user值的拷贝，这里是一个对象的引用。
- 2）调用student变量的set方法作用在这个引用对象上，**user和student同时引用的User对象内部值**被修改。
- 3）方法结束后，student变量不再使用，被释放，而user还是没有变，依然指向User对象。

> **结论：**显然，User的值被改变了，但是这是将最开始所对应得值改变了，把User的本身属性改变了，才会进行值得变化，虽然看似是按引用传递值，但是实际上是将值改变了。

- 到这里估计不少人都蒙逼了，下面我们通过一个反例来说明。

```java
package github.method;

/**
 * java中的按值调用
 * @author subeiLY
 * @create 2021-05-27 10:17
 */
public class HomeWork03 {

    /**
     * 交换两个对象
     * @param x
     * @param y
     */
    public static void swap(User x,User y){
        User temp = x;
        x = y;
        y = temp;
    }

    public static void main(String[] args) {
        User user = new User("user", 26);
        User stu = new User("stu", 18);
        System.out.println("调用前user的值："+ user.getName()+","+user.getAge());
        System.out.println("调用前stu的值："+ stu.getName()+","+stu.getAge());
        swap(user, stu);
        System.out.println("调用后user的值："+ user.getName()+","+user.getAge());
        System.out.println("调用后stu的值："+  stu.getName()+","+stu.getAge());
    }

}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021062121341636.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 通过程序，会发现user和stu的值并没有发生变化，也就是方法并没有改变存储在变量user和stu中的对象引用。swap方法的参数x和y被初始化为两个对象引用的拷贝，这个方法交换的是这两个拷贝的值而已，最终，所做的事都是白费力气罢了。在方法结束后x，y将被丢弃，而原来的变量user和stu仍然引用这个方法调用之前所引用的对象。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213405956.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 这个过程也充分说明了java程序设计语言对对象采用的不是引用调用，实际上是**对象引用进行的是值传递**，当然在这里我们可以简单理解为这就是按值调用和引用调用的区别，而且必须明白即使java函数在传递引用数据类型时，也只是拷贝了引用的值罢了，之所以能修改引用数据是因为它们同时指向了一个对象，**但这仍然是按值调用而不是引用调用。**
- 总结
  - 一个方法不能修改一个基本数据类型的参数（数值型和布尔型）。
  - 一个方法可以修改一个引用所指向的对象状态，但这仍然是按值调用而非引用调用。
  - 上面两种传递都进行了值拷贝的过程。

> 以上分析借鉴了[zejian_的博文](https://blog.csdn.net/javazejian/article/details/51192130)

## 3.方法重载

- 重载就是在一个类中，有相同的函数名称，但形参不同的函数。
- 方法的重载的规则
  - 方法名称必须相同。
  - 参数列表必须不同（个数不同、或类型不同、参数排列顺序不同等）
    方法的返回类型可以相同也可以不相同。
  - 仅仅返回类型不同不足以成为方法的重载。
- 实现理论：
  - 方法名称相同时，编译器会根据调用方法的参数个数、参数类型等去逐个匹配，以选择对应的方法，如果匹配失败，则编译器报错。

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 9:46
 */
public class Demo02 {

    public static void main(String[] args) {
        int max = max(10, 20);
        System.out.println(max);

        double max2 = max2(10.0, 20.0);
        System.out.println(max);
    }

    // 比大小
    public static int max(int num1,int num2){
        int result = 0;

        if(num1==num2){
            System.out.println("num1==num2");
            return 0;   // 终止方法
        }

        if(num1>num2){
            result = num1;
        } else {
            result = num2;
        }

        return result;
    }

    // 比大小
    public static double max2(double num1,double num2){
        double result = 0;

        if(num1==num2){
            System.out.println("num1==num2");
            return 0;   // 终止方法
        }

        if(num1>num2){
            result = num1;
        } else {
            result = num2;
        }

        return result;
    }
}
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 9:28
 */
public class Demo01 {

    // main方法
    public static void main(String[] args) {
        int sum = add(1, 2);
        System.out.println(sum);

        int sum2 = add2(1, 2, 3);
        System.out.println(sum2);
    }

    // 加法
    public static int add(int a,int b){
        return a+b;
    }

    public static int add2(int a,int b,int c){
        return a+b+c;
    }
}
```

## 4.命令行传参

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 10:41
 */
public class Demo03 {
    public static void main(String[] args) {
        // args.length 数组长度
        for(int i=0;i < args.length;i++){
            System.out.println("args[" + i + "]:" + args[i]);
        }
    }
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621213344190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 5.可变参数

- JDK1.5开始，Java支持传递同类型的可变参数给一个方法。
- 在方法声明中，在指定参数类型后加一个省略号（）。
- 一个方法中只能指定一个可变参数，它必须是方法的最后一个参数。任何普通的参数必须在它之前声明。

```java
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 10:53
 */
public class Demo04 {

    public static void main(String[] args) {
        Demo04 demo04 = new Demo04();
        demo04.test(1,2,3,4,5);
    }

    public void test(int... i){
        System.out.println(i[0]);
        System.out.println(i[1]);
        System.out.println(i[2]);
        System.out.println(i[3]);
        System.out.println(i[4]);
    }
}
package github.method;

/**
 * @author subeiLY
 * @create 2021-05-27 10:53
 */
public class Demo04 {

    public static void main(String[] args) {
        // 调用可变参数的方法
        printMax(34,3,3,2,56.5);
        printMax(new double[]{1,2,3});

    }

    public static void printMax(double... numbers){
        if(numbers.length==0){
            System.out.println("没有数据！");
            return;
        }

        double result = numbers[0];

        // 排序
        for(int i=1;i<numbers.length;i++){
            if(numbers[i] > result){
                result = numbers[i];
            }
        }
        System.out.println("The max Value is " + result);
    }
}
```

## 6.递归

- A方法调用B方法，我们很容易理解！
- 递归就是：A方法调用A方法！就是自己调用自己。
- 利用递归可以用简单的程序来解决一些复杂的问题。它通常把一个大型复杂的问题层层转化为一个与原问题相似的规模较小的问题来求解，递归策略只需少量的程序就可描述岀解题过程所需要的多次重复计算，大大地减少了程序的代码量。递归的能力在于用有限的语句来定义对象的无限集合。
- 递归结构包括两个部分：
  - 递归头：什么时候不调用自身方法。如果没有头，将陷入死循环；
  - 递归体：什么时候需要调用自身方法。

```java
package github.method;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-27 12:02
 */
public class Demo05 {

    // 5! 5*4*3*2*1
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入一个数:");
        int number = scanner.nextInt();

        int test = test(number);

        System.out.println(number + "的阶乘:" + test);
    }

    public static int test(int n){
        if(n==1){
            return 1;
        }else{
            return n*test(n-1);
        }
    }
}
```

- 写一个计算器，要求实现加减乘除功能，井且能够循环接收新的数据，通过用户交互实现。

```java
package github.method;

import java.util.Scanner;

/**
 * @author subeiLY
 * @create 2021-05-27 15:40
 */
public class HomeWork04 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double sum = 0;
        while(true){
            System.out.println("请输入第一个整数:");
            double a = scanner.nextDouble();
            System.out.println("请输入第二个整数:");
            double b = scanner.nextDouble();
            System.out.println("请输入要运算的字符(+:表示加法,-:表示减法,*:表示乘法,/:表示除法)");
            String temp = scanner.next();

            switch (temp){
                case "+":
                    sum = a + b;
                    System.out.println("结果是:" + sum);
                    continue;
                case "-":
                    sum = a - b;
                    System.out.println("结果是:" + sum);
                    continue;
                case "*":
                    sum = a * b;
                    System.out.println("结果是:" + sum);
                    continue;
                case "/":
                    sum = a / b;
                    System.out.println("结果是:" + sum);
                    continue;
                default:
                    System.out.println("请输入正确的运算符号！！");
            }
        }
    }
}
```