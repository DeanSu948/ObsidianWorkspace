
# 01. Command Line Basics
考虑后续对UNIX进行更进一步学习，附上常用命令cheatsheet
![[Pasted image 20240721224705.png]]

---
# 02. 代码编译和make
正常写出来的代码本质上其实是文本文件，是没有办法直接运行的。例如C语言，写好代码后，需要先对代码文件进行编译，编译成可执行文件后才能运行程序。

那么什么是编译呢？编译就是将写好的代码翻译成计算机硬件能理解能运行的机器码。

## Separate Compilation
编译是有很多软件步骤组成的，这些软件步骤很消耗计算功率，早期电脑需要花费很多时间来编译一个大型的软件。所以一个编译过程就被分为很多个小的compilation unit来解决这个问题。每个小的unit会被编译成一个object file，然后通过linker链接起来产生一个可执行文件。
![[Pasted image 20240721231300.png]]
- gcc -c编译文件，产生.o文件
- gcc .o文件，link .o文件产生可执行文件
> 需要自行对GCC相关的flags进行学习使用

常用如下：
![[Pasted image 20240721232504.png]]

## Linker and symbols
ld会将.o文件link在一起，也会define symbols。什么是symbols呢？Symbols是编译中共享的函数和全局变量的名字。在.o文件中调用了已经定义的symbol，编译的时候相当于留下了一个placeholder。ld就是要将这些symbol的placeholder填充起来。

## Header and \#include
假设需要在一个.c文件当中调用另外一个.c文件当中的函数，如果在当前这个.c文件的开始重复一遍函数代码，这非常不便。因此，可以将.c文件抽象成一个头文件，在其他文件头采用#include的方式来引用。

不过本质上，在编译链接的时候，其实就是将对应的代码插入到#include声明处。

当然，C语言其实是有一些标准库的，例如stdio.h，标准库当中包含一些常用的函数，具体不展开。

## Make
在编译过程中，Make是一个非常好的编译系统来管理增量式的编译。可以详见：
https://www.gnu.org/software/make/manual/make.html

Make可以对要编译的文件进行单个或者多个的编译规则的编写，这样极大方便编译过程。

Sample makefile可以参见[[02-compile.pdf#page=7&selection=31,0,31,15|02-compile, page 7]]

# 03. C语言基础
## 数据类型
- char
- short
- int
- long
- long long

# sizeof
sizeof可以显示出来数据类型的size in byte，需要注意的是，sizeof本质是一个operator而非一个函数。在printf当中要显示出来需要用%lu

## 进制类型
不多赘述

## Other C types
stdint.h有些类型定义，在C99的标准当中被定义到，例如：
- int8_t
- uint8_t
- uint32_t
- int64_t

对于浮点数有：
- float，32bit
- double，64bit

C当中用