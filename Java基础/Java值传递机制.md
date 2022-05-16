# Java值传递机制

## 一、针对于方法内变量的赋值举例

```java
/**
 * Description:
 *
 * @author zygui
 * @date Created on 2020/6/25 19:21
 */
public class VarTest {
    public static void main(String[] args) {

        System.out.println("***********基本数据类型：****************");

        int m = 10;
        int n = m;
        System.out.println("m = " + m + ", n = " + n);  // 很简单, m = 10, n = 10;

        n = 20;
        System.out.println("m = " + m + ", n = " + n);  // 很简单, m = 10, n = 20;
}
```

```java
public class VarTest2 {

        System.out.println("***********引用数据类型：****************");

        Order o1 = new Order();
        o1.orderId = 1001;
        Order o2 = o1; //赋值以后，o1和o2的地址值相同，都指向了堆空间中同一个对象实体。
        System.out.println("o1.orderId = " + o1.orderId + ", o2.orderId = " +o2.orderId); // 1001, 1001

        o2.orderId = 1002;
        // 因为指向的是同一地址空间, 当o2修改该空间中的orderId后, o1的orderId也随之改变
        System.out.println("o1.orderId = " + o1.orderId + ", o2.orderId = " +o2.orderId); // 1002, 1002

    }
}

class Order {
    int orderId;
}
```



## 二、针对于方法的参数概念

- 形参：方法定义时，声明的小括号内的参数
- 实参：方法调用时，实际传递给形参的数据

## 三、Java中参数传递机制：值传递

> 规则：

- 如果参数是**基本数据类型**，此时实参赋给形参的是实参真实存储的数据值。
- 如果参数是**引用数据类型**，此时实参赋给形参的是实参存储数据的地址值。

> 推广：

- 如果变量是基本数据类型，此时赋值的是变量所保存的数据值。
- 如果变量是引用数据类型，此时赋值的是变量所保存的数据的地址值。

**传递基本数据类型**

```java
public class VarTest {
    public static void main(String[] args) {
        int m = 10;
        int n = 20;
        System.out.println("m = " + m + ", n = " + n);
        VarTest vt = new VarTest();
        vt.swap(m, n);
        System.out.println("m = " + m + ", n = " + n); // 10, 20;

    }

    public void swap(int m, int n){
        int temp = m;
        m = n;
        n = temp;
        // System.out.println("m = " + m + ", n = " + n); // 20, 10
    }
}
```

![img](https://img-blog.csdnimg.cn/20200625202443298.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTg5OTgw,size_16,color_FFFFFF,t_70)

**传递引用数据类型**

```java
public class VarTest {
    public static void main(String[] args) {
        Data data = new Data();
        data.m = 10;
        data.n = 20;
        System.out.println("m = " + data.m + ", n = " + data.n);

        // int temp = data.m;
        // data.m = data.n;
        // data.n = temp;
        // System.out.println("m = " + data.m + ", n = " + data.n); // 20, 10

        VarTest vt = new VarTest();
        vt.swap(data); // 传的是data的地址值; 它们指向的是同一块内存空间
        System.out.println("m = " + data.m + ", n = " + data.n);
    }

    public void swap(Data data) {
        int temp = data.m;
        data.m = data.n;
        data.n = temp;
        System.out.println("m = " + data.m + ", n = " + data.n); // 20, 10
    }
}

class Data {
    int m;
    int n;
}
```

![img](https://img-blog.csdnimg.cn/20200625203731820.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTg5OTgw,size_16,color_FFFFFF,t_70)

**练习**

![img](https://img-blog.csdnimg.cn/20200625231416495.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTg5OTgw,size_16,color_FFFFFF,t_70)	

**内存图如下**

![img](https://img-blog.csdnimg.cn/20200625231504610.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTg5OTgw,size_16,color_FFFFFF,t_70)

