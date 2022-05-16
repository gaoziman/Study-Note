# MyBatis简单全面一发入魂

## MyBatis

### 概述

#### 1、MyBatis是什么 ？有什么特点 ？

他是一款半自动化ORM持久化框架，具有较高的SQL灵活性，支持高级映射（一对一、一对多），动态SQL，延迟加载和缓存等特性，但他的数据库无关高低。

- 什么是ORM ？

  Object Relation Mapping，对象关系映射。对象指的是Java对象，关系指的是数据库中的关系模型，对象关系映射，指的就

  是在Java对象和数据库的关系模型之间建立一种对应关系，比如用一个Java的Student类，去对应数据库中的一张student表，

  类中的属性和表中的列一一对应。Student类就对应student表，一个Student对象就对应student表中的一行数据

- 为什么MyBatis是半自动化ORM框架 ？

  用mybatis进行开发，需要手动编写SQL语句。而全自动的ORM框架，如hibernate，则不需要编写SQL语句。

  用hibernate开发，只需要定义好ORM映射关系，就可以直接进行CRUD操作了。由于mybatis需要手写SQL语句，所以它有较

  高的灵活性，可以根据需要，自由地对SQL进行定制，也因为要手写SQL，当要切换数据库时，SQL语句可能就要重写，因

  为不同的数据库有不同的**方言**(Dialect)，所以mybatis的数据库无关性低。虽然mybatis需要手写SQL，但相比JDBC，它提供

  了输入映射和输出映射，可以很方便地进行SQL参数设置，以及结果集封装。并且还提供了**关联查询**和**动态SQL**等功能，极

  大地提升了开发的效率。并且它的学习成本也比hibernate低很多

### 快速入门

只需要通过如下几个步骤，即可用mybatis快速进行持久层的开发



1. 编写全局配置文件
2. 编写mapper映射文件
3. 加载全局配置文件，生成SqlSessionFactory
4. 创建SqlSession，调用mapper映射文件中的SQL语句来执行CRUD操作

#### 原生开发实例

1、 在Navcat中创建新的数据库，mybatis，并且创建一个表student



![image-20220321142225501](C:\Users\lemon\AppData\Roaming\Typora\typora-user-images\image-20220321142225501.png)



2、 打开IDEA，创建一个maven工程



![image-20220321143101186](C:\Users\lemon\AppData\Roaming\Typora\typora-user-images\image-20220321143101186.png)

