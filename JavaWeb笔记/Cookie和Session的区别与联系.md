# Cookie和Session的区别与联系

## Session

- Session用来实现用户会话
- Session对应类名:HttpSession（jarkata.servlet.http.HttpSession）
- Session是JSP内置的对象

## 会话的理解

用户打开浏览器，客户端和服务器之间发生的一系列连续的请求和响应，最后把浏览器关闭，这个过程叫做一次会话。会话在服务器端有对应的 Java 对象—Session

以我自己对会话的理解来说，会话可以类比打电话，打一次电话是一次会话，电话挂断代表会话结束，那么同样的打开浏览器进行一系列操作，直到浏览器关闭才代表会话结束

`一次会话对应N个请求`

> 对于会话有了基本的理解以后，我们来看一下，它的作用是什么
>

## Session的作用

- 保存会话状态。（用户登录成功了，这是一种登录成功的状态，你怎么把登录成功的状态一直保存下来呢？使用session对象可以保留会话状态。）

> 为什么不用request或者ServletContest来保存会话状态

- request.setAttribute()存，request.getAttribute()取，ServletContext也有这个方法。request是请求域
- ServletContext是应用域。ServletContext对象是服务器启动的时候创建，服务器关闭的时候销毁，这个ServletContext对象只有一个。

> request对象的生命周期太短了。

以在淘宝买东西作为例子：我们要买东西，先把商品加入购物车，我们是不是想要每一次请求都放在同一个购

物车里面，但是request对象是一次请求一个，如果使用它的话，你会发现，每次请求放的购物车都不一样，

你是不是很郁闷，所以不能使用request对象存放会话状态，如果我们使用的是ServletContext的话，那么就

会变成所有用户共享一个购物车，最后你会发现购物车一堆的商品，所以也不适合。

`既然Session是用来保存会话状态的，那么我们就会有一个疑惑，为什么要用它来保存会话状态。因为客户端发送请求以后，它和服务器的连接就断开了。`

![img](https://img-blog.csdnimg.cn/2fb3e784155a426db026665007d697db.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

这就涉及到HTTP 协议的无状态特点，相信大家可能也有困惑，所以在正式说明Session的原理以前，我先来给大家说一下，HTTP协议的无状态特点是什么意思

## HTTP协议的无状态特点

服务器没有办法识别每一次请求是从哪一台电脑访问的，它能接收请求，但是它不知道这个请求是从哪里来的，不知道要响应给谁。比如说我们买东西，添加购物车，由于它无法识别是来自哪一个客户端的请求，它就可能把我们的请求发送给其他人，所以必须要有一种技术来让服务器知道请求来自哪里，这就是会话技术

![img](https://img-blog.csdnimg.cn/7a2259760f8a4077aec01a7db2fc08f2.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

## Session的实现原理(重点)

> Session对象是存储在服务器中的

我在下面这个图对Session对象的创建做了很清楚的说明了，我相信大家看了应该都能挺清楚的，而不是含含糊糊的。

由于下面的图片中，出现了Session超时机制，我现在就举个例子，给大家说明一下这个机制运用的地方。比

如说你本来登录淘宝想买东西，结果这个时候，家里面来客人了，你就去招待客人了，很长一段时间里面，都

没有再去碰过淘宝，也就是说明，在很长一段时间里面，你都没有发送请求给服务器，这个时候，服务器就会

把Session对象销毁，由于Session对象存储登录信息，你就会发现当客人走了以后，当你想要去淘宝继续买东

西的时候，还需要重新登录。因为这个系统会验证你是否曾经登录过，登录过的才可以继续访问，但是

Session对象是存储登录信息的，Session对象都已经销毁了，当然无法访问。

`Session超时机制简单来说就是长时间没有发送请求，服务器会销毁Session对象`

![img](https://img-blog.csdnimg.cn/2708cb83dd874736b2605666d80a4bbd.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

> 大家看了上面的图应该已经有了一定的理解了吧。现在是否有一个疑惑，为什么我们每一次发送请求，它都能找到同一个Session对象，而不是找到其他对象呢。就比如说同一时间有多个人在访问淘宝网站，为什么不同的人发送请求每次都可以返回他们的Session对象，为什么不会拿到其他人的Session对象。
>

**大家可以想一下有什么方法可以很好的解决呢？**

> 其实很容易可以想到，就是标记，没错吧，通过标记，我们就可以知道要返回哪一个Session对象。
>
> 我们可以给每一个Session对象生成一个编号，然后把这个编号发送给浏览器，在浏览器上面保存起来，
>
> 那我们发送请求给服务器的时候，就能自动把编号发给服务器，服务器根据这个编号来找相应的Session
>
> 对象。一个编号对应一个Session对象，这种存储方法是不是让你想到了Map集合，专业术语是Session列表

会话状态：指的是服务器和浏览器在会话过程中产生的状态信息，借助于会话状态，服务器可以把属于同一次会话的一系列请求和响应关联起来–sessionid

从一个终端发起的请求都会带有sessionid(Session对象的编号),这样我们通过id就可以标注它，服务器就知道要响应给谁，就比如说有好多人打电话给你，你手机没有来电显示，那我们是不是就得回拨电话回去，如果我们不知道电话号码不就不知道打电话给谁，但是如果显示电话号码，我们就知道打电话给谁了。

HttpSession session = request.getSession(); --用来获取Session对象

![img](https://img-blog.csdnimg.cn/d02e8c41ed82473ea2f6021223e3f38e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

`如果在同一个浏览器打开页面，他们的sessionid是一样的`

属于同一次会话的请求都有一个相同的标识符：`sessionid`

![img](https://img-blog.csdnimg.cn/5e97241c457d480c8508c9e4077a5a7b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

![img](https://img-blog.csdnimg.cn/baeafa23fe074728918a7490232a8655.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_16,color_FFFFFF,t_70,g_se,x_16)

其实sessionid是被包装成Cookie发送给浏览器的(后面会说，大家先有个印象)

## Session实现原理总结

> session的实现原理： 有缓存

JSESSIONID=xxxxxx 这个是以Cookie的形式保存在浏览器的内存中的。浏览器只要关闭。这个cookie就没有了。

- session列表是一个Map，map的key是sessionid，map的value是session对象。
- 用户第一次请求，服务器生成session对象，同时生成id，将id发送给浏览器。
- 用户第二次请求，自动将浏览器内存中的id发送给服务器，服务器根据id查找session对象。
- 关闭浏览器，内存消失，cookie消失，sessionid消失，会话等同于结束。

## Session常用方法:

Session在实际开发中是用来记录我们的用户信息的，我们不需要每一次访问都输入用户名和密码，如果登录过一次，后面可以不用再输入，但是这是有一个周期的，不可能一直存着的，默认失效时间为1800秒



| 方法                                       | 作用                                                         |
| ------------------------------------------ | ------------------------------------------------------------ |
| String getId()                             | 获取sessionID                                                |
| void setMaxInactiveInterval(int interval)  | 设置session的失效时间，时间单位为秒                          |
| int getMaxInactiveInterval()               | 获取当前session的失效时间                                    |
| void invalidate()                          | 通过键来删除对应的数据                                       |
| void removeAttribute(String key)           | 设置session立即失效，也就是销毁session对象(比如说登录一个网站以后，点击退出，我们就可以用这个方法) |
| void setAttribute(String key,Object value) | 通过键值对的形式存储数据(这个方法类似于map的put方法，可以用来存储数据，也可以用来修改数据，如果用来修改数据的话，前后两次的key要相同) |
| Object getAttribute(String key)            | 通过键来获取对应的数据                                       |

<head>
    <title>Title</title>
</head>
```jsp
<%--
  Created by IntelliJ IDEA.
  User: 17614
  Date: 2022-03-20
  Time: 11:20
  To change this template use File | Settings | File Templates.
--%>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
<%
    String id = session.getId();
    int interval = session.getMaxInactiveInterval();
%>
<%="sessionid=" + id%><br>
<%="失效时间:" + interval%>
</body>
</html>
```

![img](https://img-blog.csdnimg.cn/141bf91d63b8464b8e55dfefabd64f38.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

`还有一种方式可以查明Session的默认失效时间`

我们可以找到当时Tomcat的安装目录，点击config,找到web.xml

发现里面有这样的代码，说明Session默认失效时间是30分钟


```xml
<session-config>
    <session-timeout>30</session-timeout>
</session-config>
```

>
> 实现会话的两种方式：

cookie是浏览器提供用来存储用户信息，session是Java程序提供的，他们都可以存储信息，都可以描述一次会话，会话是客户端和服务端的交互，session作用于服务端，cookie作用于客户端

*那么我们接下来来讲一下Cookie*

## Cookie

### 基本介绍

> session的实现原理中，每一个session对象都会关联一个sessionid，例如：

![img](https://img-blog.csdnimg.cn/9f70c19d1389415a95b2557befd0481b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_20,color_FFFFFF,t_70,g_se,x_16)

> - JSESSIONID=3D537CF1206DCEEBD38E8287472C21C2
> - 以上的这个键值对数据其实就是cookie对象。
> - 对于session关联的cookie来说，这个cookie是被保存在浏览器的“运行内存”当中。
> - 只要浏览器不关闭，用户再次发送请求的时候，会自动将运行内存中的cookie发送给服务器。
> - 例如，这个Cookie: JSESSIONID=3D537CF1206DCEEBD38E8287472C21C2就会再次发送给服务器。
> - 服务器就是根据3D537CF1206DCEEBD38E8287472C21C2这个值来找到对应的session对象的。

**那么cookie怎么生成？cookie保存在什么地方？cookie有啥用？浏览器什么时候会发送cookie，发送哪些cookie给服务器？**

> cookie最终是保存在浏览器客户端上的。
>
> - 可以保存在运行内存中。（浏览器只要关闭cookie就消失了。）
> - 也可以保存在硬盘文件中。（永久保存。）

**Cookie(Java的一个类)**

- 存储数据的形式和map差不多，以键值对的形式存储数据
- Cookie在客户端存储，Session在服务端存储
- Cookie是服务端在HTTP响应中附带传给浏览器的一个小文本文件，一旦浏览器保存了某一个Cookie,在之后的请求和响应过程中，会将此Cookie来回传递，这样就可以通过Cookie这个载体完成客户端和服务端的数据交互，归根到底来说，之所以要有Cookie和Session机制，是因为HTTP协议无状态无连接协议。

## 经典案例

> - 京东商城，在未登录的情况下，向购物车中放几件商品。然后关闭商城，再次打开浏览器，访问京东商城的时候，购物车中的商品还在，这是怎么做的？我没有登录，为什么购物车中还有商品呢？
>   - 将购物车中的商品编号放到cookie当中，cookie保存在硬盘文件当中。这样即使关闭浏览器。硬盘上的cookie还在。下一次再打开京东商城的时候，查看购物车的时候，会自动读取本地硬盘中存储的cookie，拿到商品编号，动态展示购物车中的商品。
>     - 京东存储购物车中商品的cookie可能是这样的：productIds=xxxxx,yyyy,zzz,kkkk
>       注意：cookie如果清除掉，购物车中的商品就消失了。
>     - 126邮箱中有一个功能：十天内免登录
> - 这个功能也是需要cookie来实现的。
>   - 怎么实现的呢？
>     - 用户输入正确的用户名和密码，并且同时选择十天内免登录。登录成功后。浏览器客户端会保存一个cookie，这个cookie中保存了用户名和密码等信息，这个cookie是保存在硬盘文件当中的，十天有效。在十天内用户再次访问126的时候，浏览器自动提交126的关联的cookie给服务器，服务器接收到cookie之后，获取用户名和密码，验证，通过之后，自动登录成功。
>   - 怎么让cookie失效？
>     - 十天过后自动失效。
>     - 或者改密码。
>     - 或者在客户端浏览器上清除cookie。
>     - cookie机制和session机制其实都不属于java中的机制，实际上cookie机制和session机制都是HTTP协议的一部分。php开发中也有cookie和session机制，只要是你是做web开发，不管是什么编程语言，cookie和session机制都是需要的。
>   - HTTP协议中规定：任何一个cookie都是由name和value组成的。name和value都是字符串类型的。
> - 在java的servlet中，对cookie提供了哪些支持呢？
>   - 提供了一个Cookie类来专门表示cookie数据。jakarta.servlet.http.Cookie;
>   - java程序怎么把cookie数据发送给浏览器呢？response.addCookie(cookie);
> - 在HTTP协议中是这样规定的：当浏览器发送请求的时候，会自动携带该path下的cookie数据给服务器。（URL。）
> - 创建cookie Cookie cookie=new Cookie(String name,String value);
>   response.addCookie(cookie); 每一个浏览器都有不同的cookie



```jsp
<%
//    public Cookie(String name, String value)
    Cookie cookie=new Cookie("name","张三");
    response.addCookie(cookie);
//    读取cookie
    Cookie[] cookies = request.getCookies();
    for (Cookie cookie1 :cookies) {
        out.write(cookie1.getName()+": "+cookie1.getValue()+"<br>");

    }
%>
```

![img](https://img-blog.csdnimg.cn/6f3333744f694d5e83b360e69cb3e26c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_14,color_FFFFFF,t_70,g_se,x_16)

## Cookie常用方法

| 方法                    | 用途                           |
| ----------------------- | ------------------------------ |
| void setMaxAge(int age) | 设置Cookie的有效时间，单位为秒 |
| int getMaxAge()         | 获取Cookie的有效时间           |
| String getName/()       | 获取Cookie的name               |
| String getValue()       | 获取Cookie的value              |

## Session和Cookie的区别

- Session:保存在服务器，Session是一个对象保存在Java虚拟机中
- 保存的数据是Object
- 随着会话的结束而销毁
- 保存重要信息

**Cookie:保存在浏览器**

- 只能保存String类型，类似于文本文件，存放的都是数据，而不是对象
- 可以长期保存在浏览器，与会话无关
- 保存不重要信息

> 存储用户信息：

- Session:setAttribute(name,“admin”) 存
- getAttribute(name) 取
- 生命周期：服务端:只要WEB应用重启或者销毁
- 客户端:只要浏览器关闭就销毁
- 退出登录:session.invalidate();
- Cookie:
- Cookie cookie=new Cookie(name,“admin”);
- response.addCookie(cookie); 存

> 取数据
>

```java
Cookie[] cookies=request.getCookie();
	for(Cookie cookie:cookies){
			if(cookie.getName().equals("name"){
					out.write("欢迎回来"+cookie.getValue());
		}
```
>
> 生命周期：

不会随着服务端的重启而销毁，客户端：默认是只要关闭浏览器就会销毁，我们通过setMaxAge()方法来设置有效期，一旦设置了有效期，就不会随着浏览器的关闭而销毁，而是由设置的时间来决定
退出登录:setMaxAge(0)

> Cookie是浏览器提供的一种技术，通过服务器的程序能把一些只须保存在客户端，或者在客户端进行处理的数据放在本地计算机上，不需要通过网络传送，因此提高网页处理效率，并且可以减少服务器的负载，但是因为Cookie是服务器端保存在客户端的信息，所以它的安全性也是很差的，例如：常见的记住密码就可以通过Cookie来实现
>

如果想要把Cookie随着响应发送到客户端，需要先添加到response对象中

**cookie默认是关闭浏览器失效**

## Cookie的有效时间取值

### cookie注意点

1. cookie保存在当前浏览器，不能跨浏览器，更不用说换电脑了
2. cookie存中文问题
   - cookie不能存中文，如果有中文，则通过URLEncoder.encode()来进行编码
     通过URLDecoder.decode()进行解码
   - ![img](https://img-blog.csdnimg.cn/589688b16d7f4c4f8d8d6a1bf5d1215c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASmF2YeeahOWtpuS5oOS5i-i3rw==,size_19,color_FFFFFF,t_70,g_se,x_16)
3. 同名cookie问题
   如果服务器发送重复的cookie，那么会覆盖原来的cookie
4. cookie的数量
   不同浏览器对cookie有限定，cookie的存储是有上限的，cookie存储在客户端(浏览器)的，而且一般是由服务器创建和指定，后期结合Session来实现会话追踪

- Cookie的路径问题
  - Cookie的setPath（可以设置cookie的路径，这个路径直接决定服务器的请求是否会从浏览器中加载某些cookie

> 情景一：当前服务器下的任何项目的任意资源都可以获取Cookie对象
>

```java
//当前项目路径s
Cookie cookie=new Cookie("xxx","xxx");
//设置路径为"/",表示在当前项目下的任何项目都可以访问到cookie对象

cookie.setPath("/");
response.addCookie(cookie);
```
>
> 情景二：当前项目下的资源都可获取Cookie对象(默认不设置Cookie的path)

```java
当前项目路径s
Cookie cookie=new Cookie("xxx","xxx");
//设置路径为"/s",表示在当前项目下的任何项目都可以访问到cookie对象
//默认情况下可以不设置path的值
cookie.setPath("/s");
 	response.addCookie(cookie);
```

> 情景三：指定项目下的资源可获取Cookie对象

```java
当前项目路径s
Cookie cookie=new Cookie("xxx","xxx");
//设置路径为"/s2",表示在s2项目下才可以访问到
cookie.setPath("/s2");
//只能在s2项目下获取cookie，就算cookie是s产生的，s也不能获取它
 	response.addCookie(cookie);
```

> 情景四：指定目录下的资源可获取Cookie对象

```java
//当前项目路径s
Cookie cookie=new Cookie("xxx","xxx");
//设置路径为/s/cook,表示在s1/cook目录下面才可以访问到cookie对象
cookie.setPath("/s/cook");
response.addCookie(cookie)
```

## Cookie禁用问题

Cookie禁用了，session还能找到吗？

cookie禁用就是说服务器正常发送cookie给浏览器，但是浏览器不要了。拒收了。并不是服务器不发了。
找不到了。每一次请求都会获取到新的session对象。

> cookie禁用了，session机制还能实现吗？

可以。需要使用URL重写机制。

http://localhost:8080/servlet12/test/session;jsessionid=19D1C99560DCBF84839FA43D58F56E16

> URL重写机制会提高开发者的成本。开发人员在编写任何请求路径的时候，后面都要添加一个sessionid，给开发带来了很大的难度，很大的成本。所以大部分的网站都是这样设计的：如果禁用cookie，就别用了。
> 