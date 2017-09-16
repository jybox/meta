---
title: 强弱类型、动静类型、GC 和 VM
permalink: categories-of-languages
tags:
  - 编程语言
date: 2016-12-12
---

## 强类型 Vs. 弱类型

- 强和弱是一个相对的概念，强是指倾向于将未定义的行为视作错误（Java、Python），弱是指倾向于进行隐式的转换、忽略类型相关的错误（JavaScript）。
- 很多设计得不够严谨的语言，虽然大多数情况下（或者我们通常鼓励大家这么做）是强类型的，但也有弱类型的部分（PHP）
- 还有的语言因为提供的抽象能力很弱，我们不得不去用弱类型的部分（C）
- 鸭子类型（duck typing）是强弱类型的一个折中（常见于动态类型中，例如 Python），兼顾了灵活性和严谨性。
- 我们认为弱类型是为了方便，而强类型是为了尽早发现错误。

## 动态类型 Vs. 静态类型

- 静态类型的变量的类型是在编译时确定的（C++、Java）；动态类型的类型是在运行时确定的（JavaScript、Python），例如你可以在一个 if 的两个分支里给一个变量赋值不同的类型。
- 有的动态类型语言也会添加编译期的类型检查（TypeScript、Python），但因为语言本身的动态性，这些检查仅能覆盖一部分情况。
- 在动态类型的语言中因为类型不那么重要，所以很多时候甚至没有提供指定类型的语法（隐含了运行时的自动推导）；而在静态类型语言里通常需要为变量指定类型，所以才有了编译期自动类型推导来提供便利，而动态类型语言则做不到这一点（因为不能在编译期确定类型，更无从推导）。
- 我们认为静态类型有助于在编译时发现有关类型的错误，确定的类型也给了编译期更多的优化空间；而动态类型给了开发者更高的灵活度。

## 垃圾回收 Vs. 无垃圾回收

- 无 GC 是指代码必须自行管理申请到的内存并在恰当的时机释放（Rust、C/C++）；而有 GC 的语言会通过引用计数（PHP<5.3）、标记复制（V8）等方式定期查找无用的内存进行释放。
- 标记复制的 GC 的过程通常会引起线程的暂停，也会花费额外的 CPU；但 GC 对于建立高层次的抽象又是必不可少的：异常、闭包等（虽然 C++ 在无 GC 的情况下也实现了这两个特性，但也引入了非常高的复杂度）。
- 我们认为有 GC 可以简化对内存的管理，建立复杂的抽象；而无 GC 可以得到更底层的对内存的控制，带来更好的性能，避免因为 GC 造成的卡顿。

## 虚拟机 VS. 本地代码

- 虚拟机是指在语言和 CPU 之间还有一个用于进行翻译的层次（JavaScript、Java）；无虚拟机是指编译器直接生成本地代码给 CPU 执行（C/C++、Golang）。
- 虚拟机也提供了更为复杂的运行时的动态特性，但这些特性有的时候也可以在没有虚拟机的情况下实现（例如 C++ 的运行时类型识别、Go 的 GC）。
- 虚拟机可以以解释的方式执行（Python，将代码视作一种数据指令来执行），也可以即时编译（JIT）的方式来执行（V8，先将代码编译到本地代码然后执行），有时也会混合这两种方式（为了更快的启动速度）。
- 我们认为无虚拟机的语言可以在更低的层次和其他程序交互，同时也天然地有着更好的性能；而有虚拟机的语言则可以轻松地跨平台，针对特定的架构在运行时即时编译出更高性能的代码。

## 小结

语言 | 强类型 | 动态类型 | 垃圾回收 | 虚拟机
-------- | --- | --- | --- | ---
C |  |  |  |
C++ | Y |  |  |
Java | Y |  | Y | Y
Python | Y | Y | Y | Y
JavaScript |  | Y | Y | Y
PHP |  | Y | Y | Y
Golang | Y |  | Y |
Rust | Y |  |  |

参考来源：

- https://www.zhihu.com/question/19918532
- http://eli.thegreenplace.net/2006/11/25/a-taxonomy-of-typing-systems/