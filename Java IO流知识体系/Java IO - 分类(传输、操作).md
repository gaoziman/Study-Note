> 本文主要从`传输方式`和`数据操作`两个方面分析Java IO的分类。@Eason Gao



[Java IO - 分类(传输，操作)](#java-io---分类传输操作)

- IO理解分类 - 从传输方式上
  - [字节流](#字节流)
  - [字符流](#字符流)
  - [字节流和字符流的区别](#字节流和字符流的区别)
  - [字节转字符Input/OutputStreamReader/Writer](#字节转字符inputoutputstreamreaderwriter)
- IO理解分类 - 从数据操作上
  - [文件(file)](#文件file)
  - [数组([\])](#数组)
  - [管道操作](#管道操作)
  - [基本数据类型](#基本数据类型)
  - [缓冲操作](#缓冲操作)
  - [打印](#打印)
  - [对象序列化反序列化](#对象序列化反序列化)
  - [转换](#转换)

# Java IO - 分类(传输，操作

## IO理解分类 - 从传输方式上

从数据传输方式或者传输角度来看，可以将IO类分为 ：

- 字节流

- 字符流

  ``字节``是给计算机看的，``字符``才是给我们看的。

### 字节流

![img](https://pdai.tech/_images/io/java-io-category-1.png)

### 字符流

![img](https://pdai.tech/_images/io/java-io-category-2.png)

### 字节流和字符流的区别

- 字节流读取单个字节 ，字符流读取单个字符（一个字符的根据编码的不同，对应的字节也不同，如UTF-8是3个字节，中文编码是2个字节。）
- 字节流用来处理二进制文件（图片、MP3、视频文件等）字符流用来处理文本文件（可以看做特殊的二进制文件，使用了某种编码，让我们也可以阅读。）

> 简而言之，字节是个计算机看的，字符才是给人看的。

### 字节转字符Input/OutputStreamReader/Writer



编码就是把字符转换为字节，而解码是把字节重新组合成字符。

如果编码和解码过程使用不同的编码方式那么就出现了乱码。



- GBK 编码中，中文字符占 2 个字节，英文字符占 1 个字节；
- UTF-8 编码中，中文字符占 3 个字节，英文字符占 1 个字节；
- UTF-16be 编码中，中文字符和英文字符都占 2 个字节。

UTF-16be 中的 be 指的是 Big Endian，也就是大端。相应地也有 UTF-16le，le 指的是 Little Endian，也就是小端。

Java 使用双字节编码 UTF-16be，这不是指 Java 只支持这一种编码方式，而是说 char 这种类型使用 UTF-16be 进行编码。char 类型占 16 位，也就是两个字节，Java 使用这种双字节编码是为了让一个中文或者一个英文都能使用一个 char 来存储。



<img src="https://pdai.tech/_images/io/java-io-1.png" alt="img" style="zoom:150%;" />

## io理解分类 - 从数据操作上

从数据源或者操作角度来看 ， IO可以分类为 ：

<img src="https://pdai.tech/_images/io/java-io-category-3.png" alt="img"  />

### 文件（file）

FileInputStream、FileOutputStream、FileReader、FileWriter

### 数组([])

- 字节数组(byte[]): ByteArrayInputStream、ByteArrayOutputStream
- 字符数组(char[]): CharArrayReader、CharArrayWriter

### 管道操作

PipedInputStream、PipedOutputStream、PipedReader、PipedWriter

### 基本数据类型

DataInputStream、DataOutputStream

### 缓冲操作

BufferedInputStream、BufferedOutputStream、BufferedReader、BufferedWriter

### 打印

PrintStream、PrintWriter

### 对象序列化反序列化

ObjectInputStream、ObjectOutputStream

### 转换

InputStreamReader、OutputStreamWriter