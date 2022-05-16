# Lambda 表达式及函数式接口

## 1、函数式编程思想概述

> ​				在数学中，函数就是有输入量、输出量的一套计算方案，也就是“拿什么东西做什么事情”。相对而言，面向对象过 分强调“必须通过对象的形式来做事情”，而函数式思想则尽量忽略面向对象的复杂语法——强调做什么，而不是以 什么形式做。 面向对象的思想: 做一件事情,找一个能解决这个事情的对象,调用对象的方法,完成事情. 函数式编程思想: 只要能获取到结果,谁去做的,怎么做的都不重要,重视的是结果,不重视过程 .	

## 2、冗余的Rinnable代码

> 当需要启动一个线程去完成任务时，通常会通过 java.lang.Runnable 接口来定义任务内容，并使用 java.lang.Thread 类来启动该线程。代码如下：
>

```java
public class Demo01Runnable {
    public static void main(String[] args) {
// 匿名内部类
        Runnable task = new Runnable() {
            @Override
            public void run() { // 覆盖重写抽象方法
                System.out.println("多线程任务执行！");
            }
        };
        new Thread(task).start(); // 启动线程
    }

```

**代码分析**

> ​	对于Runnable的匿名内部类用法, 可以分析出几点内容
>

- Thread类需要Runnable接口作为参数,其中的抽象方法run方法是用来指定线程任务的内容的核心.
- 为了指定run的方法体, 不得不需要实现Runnable接口的实现类.
- 为了省去定义一个RunnableImpl实现类的麻烦, 不得不使用匿名内部类的方式.
- 必须覆盖重写抽象run方法.
- 实际上,可以发现只有run方法体才是关键所在.

## 3、体验Lambda的更优写法

```java
public class Demo02LambdaRunnable {
    public static void main(String[] args) {
        new Thread(() ‐ > System.out.println("多线程任务执行！")).start(); // 启动线程
    }
```

> 首先, 先使用实现类、匿名内部类的方式.然后和Lambda表达式对比. 要启动一个线程, 需要创建Thread类的对象并调用start方法. 为了指定线程执行的内容, 需要调用Thread类的构造方法.
>
> public Thread(Runnable target)

**使用实现类**

`为了获取Runable接口的实现对象, 可以为改接口定义一个实现类RunnableImpl:`

```java
public class RunnableImpl implements Runnable {
    @Override
    public void run() {
        System.out.println("多线程任务执行！");
    }
```

`然后创建该实现类的对象作为Thread类的构造方法`

```java
public class Demo03ThreadInitParam {
    public static void main(String[] args) {
        Runnable task = new RunnableImpl();
        new Thread(task).start();
    }
```

**使用匿名内部类**

> 这个 RunnableImpl 类只是为了实现 Runnable 接口而存在的，而且仅被使用了唯一一次，所以使用匿名内部类的
> 语法即可省去该类的单独定义，即匿名内部类：

```java
public class Demo04ThreadNameless {
    public static void main(String[] args) {
        new Thread(new Runnable() {
            @Override
            public void run() {
                System.out.println("多线程任务执行！");
            }
        }).start();
    }
```

*匿名内部类的*好处与弊端:*
       一方面，匿名内部类可以帮我们省去实现类的定义；另一方面，匿名内部类的语法——确实太复杂了！* 

> 仔细分析该代码中的语义， Runnable 接口只有一个 run 方法的定义：
>
> - public abstract void run();
>   即制定了一种做事情的方案（其实就是一个函数）：
> - 无参数：不需要任何条件即可执行该方案。
> - 无返回值：该方案	不产生任何结果。
> - 代码块（方法体）：该方案的具体执行步骤。
>   同样的语义体现在 Lambda 语法中，要更加简单：
> - () ‐> System.out.println("多线程任务执行！")
> - 前面的一对小括号即 run 方法的参数（无），代表不需要任何条件；
> - 中间的一个箭头代表将前面的参数传递给后面的代码；
> - 后面的输出语句即业务逻辑代码。

## 4、Lambda标准格式

>  Lambda省去面向对象的条条框框，格式由3个部分组成：
>

- 一些参数

- 一个箭头

- 一段代码

  Lambda 表达式的 标准格式 为：

> (参数类型 参数名称 ) ‐> { 代码语句 }

格式说明：

- 小括号内的语法与传统方法参数列表一致：无参数则留空；多个参数则用逗号分隔。
- -> 是新引入的语法格式，代表指向动作。
- 大括号内的语法与传统方法体要求基本一致。

## 5、练习

> 需求 :
> 使用数组存储多个Person对象
> 对数组中的Person对象使用Arrays的sort方法通过年龄进行升序排序
> 注意: 使用Lambda表达式时, 接口必须是函数式接口(接口内只能有一个抽象方法)

```java
package com.sunny.lambda02;
 
public class Person {
    private String name;
    private int age;
 
    public Person() {
    }
 
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
 
    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
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

```java
package com.sunny.lambda02;
 
import java.util.Arrays;
import java.util.Comparator;
 
public class ArraysDemo {
    public static void main(String[] args) {
        Person[] arr = {
                new Person("杨幂", 20),
                new Person("潘盼盼", 24),
                new Person("迪丽热巴", 13)
        };
 
        // 使用匿名内部类的方式
        Arrays.sort(arr, new Comparator<Person>() {
            @Override
            public int compare(Person o1, Person o2) {
                return o1.getAge() - o2.getAge();
            }
        });
 
        for (Person person : arr) {
            System.out.println(person.toString());
        }
 
        System.out.println("______________________");
 
        // 使用Lambda来实现.
        Arrays.sort(arr, (Person o1, Person o2) -> {
 
            return o1.getAge() - o2.getAge();
        });
 
        // 简化方式. 当抽象方法方法体中只有一条return语句时. 可以省略return
        // 若方法体重只有一条语句,那可以省略包含主体的大括号
 
        Arrays.sort(arr, (Person o1, Person o2) -> o1.getAge() - o2.getAge());
 
        for (Person person : arr) {
            System.out.println(person.toString());
        }
    }
}
```

## 6、Lambda省略格式

>  省略规则
>
> 在Lambda标准格式的基础上，使用省略写法的规则为：
>
> 1. 小括号内参数的类型可以省略；
>
> 2. 如果小括号内有且仅有一个参，则小括号可以省略；
>
> 3. 如果大括号内有且仅有一个语句，则无论是否有返回值，都可以省略大括号、return关键字及语句分号。  
>

## 7、Lambda的使用前提

> Lambda 的语法非常简洁，完全没有面向对象复杂的束缚。但是使用时有几个问题需要特别注意：
>
> - 使用Lambda必须具有接口，且要求接口中有且仅有一个抽象方法。 无论是JDK内置的 Runnable 、 Comparator 接口还是自定义的接口，只有当接口中的抽象方法存在且唯一 时，才可以使用Lambda。
> -  使用Lambda必须具有上下文推断。 也就是方法的参数或局部变量类型必须为Lambda对应的接口类型，才能使用Lambda作为该接口的实例。
> - 备注：有且仅有一个抽象方法的接口，称为“函数式接口”。
>   