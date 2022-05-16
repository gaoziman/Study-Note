# Maven从入门到精通  03-Maven 的依赖、继承与聚合

> 笔记来源：[Maven零基础入门教程（一套轻松搞定maven工具）](https://www.bilibili.com/video/BV1TW411g7hP)



# Maven 的依赖、继承与聚合

## 1、依赖

### 1.1、依赖的传递性

![image-20211129232327794](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205646360-793283316.png)

- **好处**：可以传递的依赖不必在每个模块工程中都重复声明，在“最下面”的工程中依赖一次即可
- **注意**：非 compile 范围的依赖不能传递。所以在各个工程模块中，如果有需要就得重复声明依赖

### 1.2、依赖的排除

- 需要设置依赖排除的场合

![image-20211129232635639](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205646685-1383335905.png)

- 依赖排除的设置方式

  ```xml
  复制代码123456XML<exclusions>
      <exclusion>
          <artifactid>commons-logging</artifactid>
          <groupid>commons-logging</groupid>
      </exclusion>
  </exclusions>
  ```

### 1.3、依赖的原则说明

- **作用**：解决模块工程之间的 jar 包冲突问题

- **情景设定1**：验证路径最短者优先原则

  ![image-20211129233424068](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205647291-674209904.png)

- **情景设定2**：验证路径相同时先声明者优先（先声明指的是 dependency 标签的声明顺序）

  ![image-20211129233559266](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205647479-1748764348.png)

### 1.4、统一管理依赖的版本号

![image-20211129235341043](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205647541-173724650.png)

这里对 Spring 各个jar包的依赖版本都是 4.0.0，如果需要统一升级为 4.1.1，手动修改不可靠，怎么办？

- 1）使用`properties`标签内使用自定义标签统一声明版本号

  ```xml
  复制代码123XML<properties>
      <vectorx.spring.version>4.0.0.RELEASE</vectorx.spring.version>
  </properties>
  ```

- 2）在需要统一版本的位置，使用`${自定义标签名}`引用声明的版本号

  ```xml
  复制代码
  1
  XML<version>${vectorx.spring.version}</version>
  ```

- 3）其实`properties`标签配合自定义标签声明数据的配置，并不是只能用于声明依赖的版本号。凡是需要统一声明后再引用的场合都可以使用

  ```xml
  复制代码123XML<properties>
      <project.build.sourceencoding>UTF-8</project.build.sourceencoding>
  </properties>
  ```

## 2、继承

**现状**

- Hello 依赖的 Junit 版本：4.0
- HelloFriend 依赖的 Junit 版本：4.0
- MakeFriends 依赖的 Junit 版本：4.9

由于`test`范围的依赖不能传递，所以必然会分散在各个模块工程中，很容易造成版本不一致

**需求**

- 统一管理各个模块工程中对`junit`依赖的版本

**解决思路**

- 将`junit`依赖统一提取到“父”工程中，在子工程中声明`junit`依赖时不指定版本，以父工程中统一设定的为准。同时也便于修改

**操作步骤**

1. 创建一个 Maven 工程作为父工程（注意打包方式为`pom`）

   ```xml
   复制代码1234XML<groupid>com.vectorx.maven</groupid>
   <artifactid>Parent</artifactid>
   <version>0.0.1-SNAPSHOT</version>
   <packaging>pom</packaging>
   ```

2. 在父工程中统一`junit`的依赖

   ```xml
   复制代码12345678910XML<dependencymanagement>
       <dependencies>
           <dependency>
               <groupid>junit</groupid>
               <artifactid>junit</artifactid>
               <version>4.0</version>
               <scope>test</scope>
           </dependency>
       </dependencies>
   </dependencymanagement>
   ```

3. 在子工程中声明对父工程的引用

   ```xml
   复制代码123456789XML<parent>
       <groupid>com.vectorx.maven</groupid>
       <artifactid>Parent</artifactid>
       <version>0.0.1-SNAPSHOT</version>
   </parent>
   <groupid>com.vectorx.maven</groupid>
   <artifactid>Hello</artifactid>
   <version>0.0.1-SNAPSHOT</version>
   <name>Hello</name>
   ```

4. 删除子工程坐标中与父工程重复的内容

   ![image-20211130214445099](https://img2020.cnblogs.com/blog/2364648/202112/2364648-20211203205647223-2113567334.png)

   ```xml
   复制代码12345678XML<parent>
       <groupid>com.vectorx.maven</groupid>
       <artifactid>Parent</artifactid>
       <version>0.0.1-SNAPSHOT</version>
   </parent>
   <artifactid>Hello</artifactid>
   <version>0.0.1-SNAPSHOT</version>
   <name>Hello</name>
   ```

5. 删除子工程中`junit`依赖的版本号部分

   ```xml
   复制代码12345XML<dependency>
       <groupid>junit</groupid>
       <artifactid>junit</artifactid>
       <scope>test</scope>
   </dependency>
   ```

**注意**

- 配置继承后，执行安装命令时要先安装父工程

## 3、聚合

- **作用**：一键安装各个模块工程

- **配置方式**：在一个”总的聚合工程”中配置各个参与聚合的模块

  ```xml
  复制代码1234567XML<!--配置聚合-->
  <modules>
      <!--指定各个子工程的相对路径-->
      <module>../Hello</module>
      <module>../HelloFriend</module>
      <module>../MakeFriends</module>
  </modules>
  ```

- **使用方式**：在聚合工程上进行`mvn install`即可

## 4、Web 工程的自动部署

由于原视频中使用的是`Cargo`插件，此插件较老且学习资源也很少，在这里就不做介绍和学习了。待后续学习完更多 Maven 知识再在其他章节做补充