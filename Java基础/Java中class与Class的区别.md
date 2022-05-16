# Java中class与Class的区别

## 一.class与Class区别

class是Java中的关键字，如public class Xxx 或者 class Xxx ，在声明Java类时使用。 而Class是一个类。 我们通常认为类是对象的抽象和集合，Class就相当于是对类的抽象和集合。 也可以认为对象是类的实例，类是Class的实例。

## 二.Class介绍

Class是一个类。如下图，它在java.lang包中。 ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aee8c0948b8a469c96c7d28ebadbc833~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp) 它的构造函数是private属性，所以我们不能直接new一个Class对象出来，如下图注释段所说： “私有构造函数。只有Java虚拟机创建类对象。不使用此构造函数，并阻止生成默认构造函数。” ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/769a82eb0c2244acbdc789f5a99d5f48~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp)

## 三.如何得到Class对象

### 1.通过getClass()方法获取到Class对象

getClass()方法是Object类的一部分,如下图： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1e1480ece1754ec8905ad5890e60a528~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp) 如果我们已经创建了某个类型的对象，那么我们可以通过getClass()方法来获取该类型的Class的对象：

```java
package Task;
import org.junit.Test;

public class Try0 {
    @Test
    public void toTry() throws ClassNotFoundException {
//        //forName方法：参数为其类的路径
//        Class a = Class.forName("Task.Try1");
//        System.out.println(a);

        //通过对象得到类
        Try1 try1 = new Try1();
        Class b = try1.getClass();
        System.out.println(b);
    }
}

class Try1{

}
复制代码
```

测试运行结果： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9623589a77044b93ad8e8bcde6a4995b~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp)

### 2.通过forName()方法获取到Class对象

Class.forName方法是Class类的一个静态方法,如下图： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8c097d7ddfa34ec89baf0588fff8fc0f~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp) 所以可以直接通过Class.forName("类的路径")获取Class对象：

```java
package Task;
import org.junit.Test;

public class Try0 {
    @Test
    public void toTry() throws ClassNotFoundException {
        //forName方法：参数为其类的路径
        Class a = Class.forName("Task.Try1");
        System.out.println(a);
    }
}

class Try1{

}
复制代码
```

测试运行截图： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/569b3514614a4174845412199876c50f~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp)

### 3.类.class获得Class对象（类字面常量）

```java
package Task;
import org.junit.Test;

public class Try0 {
    @Test
    public void toTry() throws ClassNotFoundException {
//        //forName方法：参数为其类的路径
//        Class a = Class.forName("Task.Try1");
//        System.out.println(a);

//        //通过对象得到类
//        Try1 try1 = new Try1();
//        Class b = try1.getClass();
//        System.out.println(b);

        //类字面常量
        Class c = Try1.class;
        System.out.println(c);
    }
}

class Try1{

}
复制代码
```

测试运行结果： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/63c2382d907e459782119c1545f255d8~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp)

## 四.Class常用方法

```java
package Task;
import org.junit.Test;

public class Try0 {
    @Test
    public void toTry() throws ClassNotFoundException {
//        //forName方法：参数为其类的路径
//        Class a = Class.forName("Task.Try1");
//        System.out.println(a);

        //通过对象得到类
        Try1 try1 = new Try1();
        Class b = try1.getClass();
        System.out.println(b);

//        //类字面常量
//        Class c = Try1.class;
//        System.out.println(c);


        //isInterface方法，判断是否为接口
        System.out.println(b.isInterface());
        //isArray方法，判断是否为数组
        System.out.println(b.isArray());
        //isPrimitive方法，判断是否是基本类型，例如int是基本类型，Integer为包装类
        System.out.println(b.isPrimitive());
        //isAnnotation方法，判断是否为注解，注解如常见的重写注解@Override，我们所用的单元测试@Test注解
        System.out.println(b.isAnnotation());
        //isInstance方法参数是一个对象，判断该对象try1对应的类Try1是否是b的对象
        System.out.println(b.isInstance(try1));
        //getClassLoader方法，获取类加载器
        System.out.println(b.getClassLoader());
        //getSuperclass方法，获取父类信息
        System.out.println(b.getSuperclass());
        //getGenericSuperclass方法，也是获取父类信息
        System.out.println(b.getGenericSuperclass());
        //getComponentType方法，如果b的类型是数组，则获取数组里元素的类型
        System.out.println(b.getComponentType());
        //getDeclaredClasses方法，获取b继承于哪个类
        System.out.println(b.getDeclaredClasses());


        //几个获取name的方法：
        //getName方法
        System.out.println(b.getName());
        //getTypeName方法
        System.out.println(b.getTypeName());
        //getCanonicalName方法
        System.out.println(b.getCanonicalName());
        //getSimpleName方法
        System.out.println(b.getSimpleName());

//        以下还有一些方法只列举出来
//        getTypeParameters方法，获取泛型类中的泛型参数数组
//        getClasses方法，获取Class对象中public修饰的内部类
//        getDeclaredClasses方法，获取Class对象中的内部类，继承成员不包含在内
//        getConstructors方法，获取public修饰的构造函数
//        getConstructor方法，查找对应的构造函数
//        getDeclaredConstructors方法，获取Class对象中的构造函数
    }
}

class Try1 {

}
复制代码
```

输出截图如下： ![在这里插入图片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/45d1ebedc9e04cc9a5d81ca55cf2e50e~tplv-k3u1fbpfcp-zoom-in-crop-mark:1304:0:0:0.awebp)



作者：YuShiwen
链接：https://juejin.cn/post/7081487324558655524
来源：稀土掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。