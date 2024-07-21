
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

# Header and \#include
