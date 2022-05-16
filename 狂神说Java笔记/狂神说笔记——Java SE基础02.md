# [狂神说笔记——Java SE基础02](https://www.cnblogs.com/gh110/p/15153668.html)

# 数组

## 1.数组概述

- 数组是相同类型数据的有序集合。
- 数组描述的是相同类型的若干个数据按照一定的先后次序排列组合而成。
- 其中每一个数据称作一个数组元素每个数组元素可以通过一个下标来访问它们。

## 2.数组声明创建

- 首先必须声明数组变量，才能在程序中使用数组。下面是声明数组变量的语法：

```java
dataType[] arrayRefVar;	// 首选的方法
或
dataType arrayRefVar[];	// 效果相同，但不是首选方法
```

- Java语言使用new操作符来创建数组，语法如下：

```java
dataType[] arrayRefVar = new dataType[arraySize];
```

- 数组的元素是通过索引访问的，数组索引从0开始。
- 获取数组长度：`arrays. length`

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-27 16:08
 */
public class ArrayDemo01 {
    // 变量的类型  变量的名字  = 变量的值

    public static void main(String[] args) {
        int[] numbers;  // 1.定义

        numbers = new int[10];  // 2.创建一个数组
        // 这里面可以存放10个int型数字

        // 3.给数组赋值
        numbers[0]=1;
        numbers[1]=2;
        numbers[2]=3;
        numbers[3]=4;
        numbers[4]=5;
        numbers[5]=6;
        numbers[6]=7;
        numbers[7]=8;
        numbers[8]=9;
        numbers[9]=10;

        System.out.println(numbers[9]);
    }

}
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-27 16:08
 */
public class ArrayDemo01 {
    // 变量的类型  变量的名字  = 变量的值

    public static void main(String[] args) {
        int[] numbers;  // 1.定义

        numbers = new int[10];  // 2.创建一个数组
        // 这里面可以存放10个int型数字

        // 3.给数组赋值
        numbers[0]=1;
        numbers[1]=2;
        numbers[2]=3;
        numbers[3]=4;
        numbers[4]=5;
        numbers[5]=6;
        numbers[6]=7;
        numbers[7]=8;
        numbers[8]=9;
        numbers[9]=10;

        // 计算所有数字的和
        int sum = 0;
        // 获取数组的长度: arrays.length
        for(int i = 0;i<numbers.length;i++){
            sum = sum + numbers[i];
        }

        System.out.println(sum);
    }

}
```

> 内存分析

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215235984.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215229731.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-27 17:00
 */
public class ArrayDemo02 {
    public static void main(String[] args) {
        // 静态初始化 : 创建 + 赋值
        int[] a = {1,2,3,4,5,6,7,8};
        System.out.println(a[0]);

        // 动态初始化
        int[] b = new int[2];
        b[0]=10;

        System.out.println(b[0]);

    }
}
```

> 数组的四个基本特点：

- 其长度是确定的。数组一旦被创建，它的大小就是不可以改变的；
- 其元素必须是相同类型不允许出现混合类型。
- 数组中的元素可以是任何数据类型，包括基本类型和引用类型。
- 数组变量属引用类型，数组也可以看成是对象，数组中的每个元素相当于该对象的成员变量数组本身就是对象，Java中对象是在堆中的，因此数组无论保存原始类型还是其他对象类型，数组对象本身是在堆中的。

> 下标越界及小结：

- 下标的合法区间：[0, length-1]，如果越界就会报错：

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-27 17:42
 */
public class ArrayDemo03 {
    public static void main(String[] args) {
        int[] a = new int[2];
        System.out.println(a[2]);
    }
}
```

- ArraylndexOutofBounds Exception：数组下标越界异常！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215219277.png#pic_center)

- 数组是相同数据类型（数据类型可以为任意类型）的有序集合数组也是对象。
- 数组元素相当于对象的成员变量。
- 数组长度的确定的，不可变的。如果越界，则报：ArrayIndexOutofBounds。

## 3.数组使用

- 普通的for循环
- For-Each循环
- 数组作方法入参
- 数组作返回值

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-28 13:57
 */
public class ArrayDemo04 {
    public static void main(String[] args) {
        int[] arrays = {1,2,3,4,5,6};

        // JDK1.5，没有下标
//        for(int array:arrays){
//            System.out.println(array);
//        }

//        printArray(arrays);

        int[] reverse = reverse(arrays);
        printArray(reverse);

    }
    // 打印数组元素
    public static void printArray(int[] arrays){
        for(int i=0;i< arrays.length;i++){
            System.out.println(arrays[i]+"");
        }
    }

    // 反转数组
    public static int[] reverse(int[] arrays){
        int[] result = new int[arrays.length];

        // 反转的操作
        for (int i = 0,j= result.length-1; i < arrays.length; i++,j--) {
//            result[] = arrays[i];
            result[j] = arrays[i];
        }

        return result;
    }
}
```

## 4.多维数组

- 多维数组可以看成是数组的数组，比如二维数组就是一个特殊的一维数组，其每一个元素都是一个一维数组。
- 二维数组

```java
int a[][] = new int[2][5];
// 解析：以上二维数组a可以看成一个两行五列的数组
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215201739.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-29 17:31
 */
public class ArrayDemo05 {
    public static void main(String[] args) {
        // [4][2]
        /*
        1,2     array[0]
        2,3     array[1]
        3,4     array[2]
        5,6     array[3]
         */
        int[][] array = {{1,2},{3,4},{5,6},{7,8}};

        // 输出单个元素
        printArray(array[0]);
        System.out.println(array[0][0]);

        System.out.println("----------------");
        
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++){
                System.out.println(array[i][j]);
            }
        }
    }

    // 打印数组元素
    public static void printArray(int[] arrays){
        for(int i=0;i< arrays.length;i++){
            System.out.println(arrays[i]+"");
        }
    }
}
```

## 5.Arrays类

- 数组的工具类 javautil. Arrays
- 由于数组对象本身并没有什么方法可以供我们调用但AP中提供了一个工具类 Arrays供我们使用从而可以对数据对象进行一些基本的操作。
- 查看JDK帮助文档。
- Arrays类中的方法都是 static 修饰的静态方法在使用的时候可以直接使用类名进行调用，而"不用"使用对象来调用（注意：是“不用”而不是“不能”）。
- 具有以下常用功能：
  - 给数组赋值：通过fill方法。
  - 对数组排序：通过sort方法按升序。
  - 比较数组：通过 equals方法比较数组中元素值是否相等。
  - 查找数组元素：通过 binarySearch方法能对排序好的数组进行二分查找法操作。

```java
package github.array;

import java.util.Arrays;

/**
 * @author subeiLY
 * @create 2021-05-29 18:24
 */
public class ArrayDemo06 {
    public static void main(String[] args) {
        int[] a = {1,2,3,4,9090,543,21,3,23};

        System.out.println(a);  // 地址值：[I@14ae5a5

        // 打印数组元素Arrays.toString
        System.out.print("系统打印数组方法:");
        System.out.println(Arrays.toString(a));
        System.out.print("自定义打印数组方法:");
        printfArray(a);

        // 数组排序
        Arrays.sort(a);

        System.out.println(Arrays.toString(a));

        // 数组填充
        Arrays.fill(a,2,4,12);  // 数组2~4之间填充12
        System.out.println("数组填充:" + Arrays.toString(a));

        // 数组查找
        int i = Arrays.binarySearch(a, 23);
        System.out.println("查找的元素在数组中的位置:" + i);
    }

    public  static void printfArray(int[] a){
        for (int i = 0; i < a.length; i++) {
            if(i==0){
                System.out.print("[");
            }
            if(i==a.length-1){
                System.out.print(a[i] + "]");
            }else {
                System.out.print(a[i] + ", ");
            }
        }
        System.out.println();
    }
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215149893.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 6.冒泡排序

- 冒泡排序无疑是最为出名的排序算法之一，总共有八大排序！
- 两层循环，外层冒泡轮数，里层依次比较。
- 这个算法的时间复杂度为O(n2)。

```java
package github.array;

import java.util.Arrays;

/**
 * @author subeiLY
 * @create 2021-05-29 21:17
 */
public class ArrayDemo07 {
    public static void main(String[] args) {
        // 调用排序
        int[] array = {12,63,1,95,44,62,78};
        System.out.println("排序前:" + Arrays.toString(array));
        int[] sort = sort(array);   // 调用自定义冒泡排序函数
        System.out.println("排序后:" + Arrays.toString(sort));

    }
    // 冒泡排序
    /*
    1.比较数组中，两个相邻的元素，如果第一个数比第二个数大，我们就交换他们的位置。
    2.每一次比较，都会产生出一个最大或最小的数。
    3.下一轮则可以少一次排序！
    4.依次循环，直到结束。
     */

    public static int[] sort(int[] array){
        // 临时变量
        int temp = 0;
        // 外层循环，判断要走多少次;
        for (int i = 0; i < array.length-1; i++) {

            boolean flag = false;   // 通过flag标识位减少没有意义的比较

            // 内层循环，比较大小，如果第一个数比第二个数大，交换位置
            for (int j = 0; j < array.length-1-i; j++) {
                if (array[j] > array[j+1]) {
                    temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                    flag = true;
                }
            }
            if(flag==false){
                break;
            }
        }
        return array;
    }
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215138876.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 7.稀疏数组

- 当一个数组中大部分元素为0，或者为同一值的数组时，可以使用稀疏数组来保存该数组。
- 稀疏数组的处理方式是：
  - 记录数组一共有几行几列，有多少个不同值。
  - 把具有不同值的元素和行列及值记录在一个小规模的数组中，从而缩小程序的规模。
- 如下图：左边是原始数组，右边是稀疏数组。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215126652.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

```java
package github.array;

/**
 * @author subeiLY
 * @create 2021-05-30 15:21
 */
public class ArrayDemo08 {
    public static void main(String[] args) {
        // 1.创建一个二维数组
        int[][] array1 = new int[11][11];
        array1[1][2] = 1;
        array1[2][3] = 2;
        // 输出原始数组
        System.out.println("输出原始的数组");

        for(int[] ints:array1){
            for(int anInt : ints){
                System.out.print(anInt + "\t");
            }
            System.out.println();
        }

        System.out.println("====================");

        // 转换为稀疏数组保存
        // 获取有效值的个数
        int sum = 0;
        for(int i = 0;i < 11;i++){
            for (int j = 0; j < 11; j++) {
                if(array1[i][j]!=0){
                    sum++;
                }
            }
        }
        System.out.println("有效值的个数:" + sum);

        // 2.创建一个稀疏数组的数组
        int[][] array2 = new int[sum+1][3];

        array2[0][0] = 11;
        array2[0][1] = 11;
        array2[0][2] = sum;

        // 遍历二维数组，将非零的值，存放到稀疏数组
        int count = 0;
        for (int i = 0; i < array1.length; i++) {
            for (int j = 0; j < array1[i].length; j++) {
                if(array1[i][j]!=0){
                    count++;
                    array2[count][0] = i;
                    array2[count][1] = j;
                    array2[count][2] = array1[i][j];
                }
            }
        }

        // 输出稀疏数组
        System.out.println("稀疏数组:");

        for (int i = 0; i < array2.length; i++) {
            System.out.println(array2[i][0] + "\t"
                        + array2[i][1] + "\t"
                        + array2[i][2] + "\t");
        }

        System.out.println("===========");
        System.out.println("还原");
        // 1.读取稀疏数组
        int[][] array3 = new int[array2[0][0]][array2[0][1]];
        // 2.给元素还原值
        for (int i = 1; i < array2.length; i++) {
            array3[array2[i][0]][array2[i][1]] = array2[i][2];
        }

        // 3.打印
        System.out.println("输出原始的数组:");

        for(int[] ints:array3){
            for(int anInt : ints){
                System.out.print(anInt + "\t");
            }
            System.out.println();
        }
    }
}
```

# 面向对象

## 1.初识面向对象

- 面向过程思想
  - 步骤清晰简单，第一步做什么，第二步做什么…
  - 面对过程适合处理一些较为简单的问题。
- 面向对象思想
  - 物以类聚，分类的思维模式，思考问题首先会解决问题需要哪些分类，然后对这些分类进行单独思考。最后，才对某个分类下的细节进行面向过程的思索。
  - 面向对象适合处理复杂的问题，适合处理需要多人协作的问题！
- 对于描述复杂的事物，为了从宏观上把握、从整体上合理分析，我们需要使用面向对象的思路来分析整个系统。但是，具体到微观操作，仍然需要面向过程的思路去处理。
- 面向对象编程（ Object- Oriented Programming,OOP）
- 面向对象编程的本质就是：以类的方式组织代码，以对象的组织（封装）数据。
- 三大特征：
  - **继承**
  - **封装**
  - **多态**
- 从认识论角度考虑是先有对象后有类。对象，是具体的事物。类，是抽象的，是对对象的抽象。
- 从代码运行角度考虑是先有类后有对象。类是对象的模板。

## 2.方法回顾和加深

- 方法的定义

  - 修饰符
  - 返回类型
  - break：跳出 switch，结束循环和 return的区别。
  - 方法名：注意规范就OK，见名知意
  - 参数列表：(参数类型，参数名) …
  - 异常抛出：疑问，参考下文！

  

  ```java
  package github.oop;
  
  import java.io.IOException;
  
  /**
   * @author subeiLY
   * @create 2021-05-30 17:54
   */
  // 类
  public class Demo01 {
      // main方法
      public static void main(String[] args) {
  
      }
  
      /*
      修饰符 返回值类型 方法名(...){
          // 方法体
          return 返回值;
      }
       */
      public String sayHello(){
          return "hello,world!";
      }
  
      public int max(int a,int b){
          return a>b ? a : b; // 三元运算符
      }
  
      // 数组下标越界：Arrayindexoutofbounds
      public void readFile(String file) throws IOException{
  
      }
  }
  ```

- 方法的调用

  - 静态方法

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215059161.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 非静态方法

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621215048820.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 形参和实参
- 值传递和引用传递

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021062121491784.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214907285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- this关键字

## 3.对象的创建分析

- 类是一种抽象的数据类型它是对某一类事物整体描述/定义但是并不能代表某一个具体的事物。
- 使用new关键字创建对象。
- 使用new关键字创建的时候，除了分配内存空间之外，还会给刨建好的对象进行默认的初始化以及对类中构造器的调用。
- 类中的构造器也称为构造方法，是在进行创建对象的时候必须要调用的。并且构造器有以下俩个特点：
  - 1.必须和类的名字相同；
  - 2.必须没有返回类型也不能写void。
- 构造器：
  - 1.和类名初问
  - 2.没有返回值
- 作用：
  - 1.new本质在调用构造方法；
  - 2.初始化对象的值。
- 注意：定义有参构造之后，如果想使用无参构造，显示的定义一个无参构造。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214854736.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214844902.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214835526.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 4.面向对象三大特性

> 封装：**属性私有，get/set**

- 程序设计要追求高内聚低耦合。高内聚就是类的内部数据操作细节自己完成，不允许外部干涉；低耦合：仅暴露少量的方法给外部使用。
- 封装（数据的隐藏）：通常，应禁止直接访问一个对象中数据的实际表示，而应该通过操作接口来访问，这称为信息隐藏。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214823542.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 封装的作用：
  - 提高了代码的安全性，保护数据；
  - 隐藏代码的实现细则；
  - 统一接口；
  - 系统可维护增加了。

> 继承：**object类、super、方法重写**

- 继承的本质是对某一批类的抽象，从而实现对现实世界更好的建模。
- extands的意思是“扩展”。子类是父类的扩展。
- JAVA中类只有单继承，没有多继承！
- 继承是类和类之间的一种关系。除此之外，类和类之间的关系还有依赖、组合、聚合等。
- 继承关系的俩个类，一个为子类（派生类），一个为父类（基类）。子类继承父类使用关键字 extends来表示。
- 子类和父类之间从意义上讲应该具有"is a"的关系。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214812230.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214804323.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

------

- Super概述

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214753432.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/2021062121473490.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 私有的东西无法被继承！！！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214724961.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

**super注意点**：

1. super调用父类的构造方法，必须在构造方法的第一个
2. super必须只能出现在子类的方法或者构造方法中！
3. super和this不能同时调用构造方法！

**VSthis**：

- 代表的对象不同：
  - this：本身调用者这个对象；
  - super：代表父类对象的应用；
- 前提
  - this：没有继承也可以使用；
  - super：只能在继承条件才可以使用；
- 构造方法
  - this（）：本类的构造；
  - super（）：父类的构造。

------

- 方法的重写：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214711148.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 重写：需要有继承关系，子类重写父类的方法！

1. 方法名必须相同;
2. 参数列表列表必须相同;
3. 修饰符：范围可以扩大但不能缩小: public>Protected>Default>private
4. 抛出的异常：范围，可以被缩小，但不能扩大；ClassNotFoundException–> Exception(大)

- 重写，子类的方法和父类必要一致；方法体不同！
- 为什么需要重写：父类的功能，子类不一定需要，或者不一定满足！

> 多态：

- 即同一方法可以根据发送对象的不同而采用多种不同的行为方式。
- 一个对象的实际类型是确定的，但可以指向对象的引用的类型有很多。
- 多态存在的条件：
  - 有继承关系；
  - 子类重写父类方法；
  - 父类引用指向子类对象。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214700209.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

- 多态注意事项：
  1. 多态是方法的多态，属性没有多态；
  2. 父类和子类，有联系，类型转换异常！ClassCastException!
  3. 存在条件：继承条件，方法需要重写！父类引用指向子类对象！
     1. static 方法，属于类，它不属于实例
     2. final 常量；
     3. private 方法；

**instanceof**：判断一个对象是什么类型。

![在这里插入图片描述](https://img-blog.csdnimg.cn/202106212146499.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214638747.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/2021062121462388.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214610192.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

**static关键字**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214437197.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214450235.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214501243.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214530285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214538702.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 5.抽象类和接口

> 抽象类

- abstract修饰符可以用来修饰方法也可以修饰类如果修饰方法那么该方法就是抽象方法如果修饰类那么该类就是抽象类。
- 抽象类中可以没有抽象方法但是有抽象方法的类一定要声明为抽象类。
- 抽象类，不能使用new关键字来创建对象它是用来让子类继承的。
- 抽象方法只有方法的声明没有方法的实现它是用来让子类实现的。
- 子类继承抽象类那么就必须要实现抽象类没有实现的抽象方法否则该子类也要声明为抽象类。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214415755.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

> 接口

- 普通类：只有具体实现；
- 抽象类：具体实现和规范（抽象方法）都有！
- 接口：只有规范！
- 接口就是规范，定义的是一组规则，体现了现实世界中“如果你是…则必须能…”的思想。如果你是天使，则必须能飞。如果你是汽车，则必须能跑。如果你好人，则必须干掉坏人；如果你是坏人，则必须欺负好人。
- 接口的本质是契约，就像我们人间的法律一样。制定好后大家都遵守。
- OO的精髓，是对对象的抽象，最能体现这一点的就是接口。为什么我们讨论设计模式都只针对具备了抽象能力的语言（比如c++、java、c#等），就是因为设计模式所硏究的，实际上就是如何合理的去抽象。
- 声明类的关键字是 class，声明接口的关键字是 interface。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214401704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 6.内部类及OOP实战

- 内部类就是在一个类的内部在定义一个类，比如，A类中定义一个B类，那么B类相对A类来说就称为内部类，而A类相对B类来说就是外部类了。
  1. 成员内部类
  2. 静态内部类
  3. 局部内部类
  4. 匿名内部类

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214349556.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

# 异常

## 1.什么是异常

  实际工作中，遇到的情况不可能是非常完美的。比如：你写的某个模块，用户输入不一定符合你的要求、你的程序要打开某个文件，这个文件可能不存在或者文件格式不对，你要读取数据库的数据，数据可能是空的等。我们的程序再跑着，内存或硬盘可能满了。等等。

  软件程序在运行过程中，非常可能遇到刚刚提到的这些异常问题，我们叫异常，英文是：Exception，意思是例外。这些，例外情况，或者叫异常，怎么让我们写的程序做出合理的处理。而不至于程序崩溃。

  异常指程序运行中出现的不期而至的各种状况如：文件找不到、网络连接失败、非法参数等。异常发生在程序运行期间它影响了正常的程序执行流程。

> 要理解Java异常处理是如何工作的，需要掌握以下三种类型的异常：

- 检查性异常：最具代表的检查性异常是用户错误或问题引起的异常，这是程序员无法预见的例如要打开一个不存在文件时，一个异常就发生了，这些异常在编译时不能被简单地忽略。
- 运行时异常：运行时异常是可能被程序员避免的异常。与检查性异常相反，运行时异常可以在编译时被忽略。
- 错误ERROR：错误不是异常，而是脱离程序员控制的冋题。错误在代码中通常被忽略。例如，当栈溢出时，一个错误就发生了，它们在编译也检查不到的。

## 2.异常体系结构

- Java把异常当作对象来处理，并定义一个基类 java. lang.Throwable作为所有异常的超类。
- 在 Java API中已经定义了许多异常类，这些异常类分为两大类，错误Error和异常 Exception。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214335538.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

> Error

- Error类对象由Java虚拟机生成并抛出，大多数错误与代码编写者所执行的操作无关。
- Java虚拟机运行错误（ Virtual Machine Error），当JVM不再有继续执行操作所需的内存资源时，将出现 OutofMemory Error。这些异常发生时，Java虚拟机（JVM）一般会选择线程终止。
- 还有发生在虛拟机试图执行应用时，如类定义错误（ NoClass Deffound error）、链接错误（ Linkage Error）。这些错误是不可查的，因为它们在应用程序的控制和处理能力之外，而且绝大多数是程序运行时不允许出现的状况。

> Exception

- 在 Exception分支中有一个重要的子类 Runtime Exception（运行时异常）
  - ArraylndexOutOfBoundsException（数组下标越界）
  - NullPointerException（空指针异常）
  - ArithmeticException（算术异常）
  - Missing Resource Exception（丢失资源）
  - ClassNotFound Exception（找不到类）等异常，这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理。
- 这些异常一般是由程序逻辑错误引起的，程序应该从逻辑角度尽可能避免这类异常的发生；
- Error和 Exception的区别：Error通常是灾难性的致命的错误，是程序无法控制和处理的，当出现这些异常时，Java虛拟机（JVM）一般会选择终止线程；Exception通常情况下是可以被程序处理的，并且在程序中应该尽可能的去处理这些异常。

## 3.Java异常处理机制与处理异常

- 抛出异常
- 捕获异常
- 异常处理五个关键字：
  - try、catch、 finally、throw、throws

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214317408.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 4.自定义异常

- 使用Java内置的异常类可以描述在编程时岀现的大部分异常情况。除此之外，用户还可以自定义异常。用户自定义异常类，只需继承 Exception类即可。
- 在程序中使用自定义异常类，大体可分为以下几个步骤：
  1. 创建自定义异常类。
  2. 在方法中通过 throw关键字抛出异常对象。
  3. 如果在当前抛出异常的方法中处理异常，可以使用try- catch语句捕获并处理；否则在方法的声明处通过 throws关键字指明要抛岀给方法调用者的异常，继续进行下一步操作。
  4. 在出现异常方法的调用者中捕获并处理异常。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210621214304440.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzQ2MTUzOTQ5,size_16,color_FFFFFF,t_70#pic_center)

## 5.总结

- 处理运行时异常时，采用逻辑去合理规避同时辅助 try-catch ；
- 处理在多重 catch块后面，可以加一个 catch（ Exception）来处理可能会被遗漏的异常；
- 对于不确定的代码，也可以加上try- catch，处理潜在的异常；
- 尽量去处理异常，切忌只是简单地调用 printStackTrace0去打印输出；
- 具体如何处理异常，要根据不同的业务需求和异常类型去决定；
- 尽量添加 finally！语句块去释放占用的资源。