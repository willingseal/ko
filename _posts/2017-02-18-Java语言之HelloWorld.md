---

layout: post

title: "Java语言之HelloWorld"

categories:

- Java

tags:

- Java

---

在安装Android Studio的时候先把Java第一个程序HelloWorld跑起来吧

#### 安装java开发环境

系统版本：macOS 10.12.3 

```
➜  ~ java -version
No Java runtime present, requesting install.
```
Mac上没有java，需要安装JDK。
[前往JDK下载安装](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
![根据自己的系统下载对应的](/assets/images/2017-02-18-001.png)

看看安装好的java版本
```
➜  ~ java -version
java version "1.8.0_121"
Java(TM) SE Runtime Environment (build 1.8.0_121-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.121-b13, mixed mode)
```

#### Java之HelloWorld

[Java基础教程](http://www.runoob.com/java/java-tutorial.html)

```java
public class HelloWorld {
    public static void main(String []args) {
        System.out.println("Hello World");
    }
}
```


```
// 报错
➜  Desktop javac helloWorld.java
helloWorld.java:1: 错误: 类HelloWorld是公共的, 应在名为 HelloWorld.java 的文件中声明
public class HelloWorld {
       ^
1 个错误

//编译
➜  Desktop javac HelloWorld.java

//运行
➜  Desktop java HelloWorld
Hello World
```

![运行成功后多了一个HelloWorld.class文件](/assets/images/2017-02-18-002.png)



后续：学习完java基础语法之后，补充java语言的特性，与其他语言的对比。

