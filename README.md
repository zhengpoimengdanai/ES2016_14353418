#嵌入式Lab3实验报告

##Description
###DOL是一个框架，基本上由三部分组成

###1.应用程序编程
DOL定义了一组程序，应用程序员可以使用这些程序编写程序，而无需了解底层架构详细知识

###2.仿真功能

提供程序员测试应用程序的功能仿真框架。

###3.映射优化

DOL映射优化是计算一组应用程序到形状架构平台的最佳映射。

##How to install

###1.下载文件
此处用systemc举例，因为文件已经被拖入虚拟机中所以显示已删除

![img](https://cl.ly/2Q280t2r1p2T/Image%202016-10-09%20at%2010.05.36%20PM.png)

###2.解压文件

![img](https://cl.ly/1n0u250W2n3O/Image%202016-10-09%20at%2010.11.25%20PM.png)

（systemc的那句出来的解压文件的语句将命令语句直接刷走了就不截图了= =）

###3.编译systemc
cd systemc-2.3.1

mkdir objdir


cd objdir


../configure CXX=g++ --disable-async-updates

![img](https://cl.ly/2O2f2b1u1h01/Image%202016-10-09%20at%2010.15.49%20PM.png)

运行之后

![img](https://cl.ly/31170m2A3d3W/Image%202016-10-09%20at%2010.17.31%20PM.png)

sudo make install

pwd记录下当前路径

![img](https://cl.ly/352w0E2b131W/Image%202016-10-09%20at%2010.20.21%20PM.png)

cd ../dol
修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，

property name="systemc.inc" value="YYY/include"

property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"

把YYY改成上页pwd的结果

###编译DOL

ant -f build_zip.xml all

![img](https://cl.ly/1S3N423G2j2G/Image%202016-10-09%20at%2010.25.01%20PM.png)

最后运行第一个例子试验

cd build/bin/main

ant -f runexample.xml -Dnumber=1


![img](https://cl.ly/0a1G012A2F3C/Image%202016-10-09%20at%2010.26.43%20PM.png)
##Experimental experience

学习了makedown语法和使用，懂得了如何使用github