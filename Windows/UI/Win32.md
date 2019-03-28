# Win32程序：01-简介
>Win32是经典的Windows GUI开发SDK，目前依然在被广泛应用，是最原生、执行效率最高的GUI程序。

## 概念

1. Win32程序

WinAPI，也叫Win32程序，是之运行在Win32环境中的应用程序。WinAPI是Windows GUI的原生接口，所有人都可以利用这套API来在Windows上显示窗体和使用Windows的消息机制。核心文件为Windows.h，Windows GUI的入口函数为WinMain函数。Win32是Windows的运行时环境。早期系统为32位因此叫Win32，运行在Win32上的程序叫Win32程序，后来有了64位系统后，这种程序依然沿用Win32程序的叫法，只不过64位系统上调用的是64位的Windows.h，开发者无需关心系统的位数。一切在Windows上的GUI程序或框架都是基于WinAPI的，比如Java、QT等等。

1. MFC框架

全称-微软基础类(Microsoft Foundation Classes)，MFC最初是为Windows提供面向对象的编程，其API全部使用C++实现。由于WinAPI是C语言，MFC对其进行封装并为开发者提供了更便利的API。由于Win32的API比较底层，操作繁琐，开发者通常需要耗费大量的时间在一些基础工作上，比如事件监听、基础UI的定制、消息流等等，MFC对这些繁琐的功能进行了封装，并且添加了许多额外的功能，比如数据库操作，使得开发者可以专注程序的核心功能而非重复基本工作。

1. COM组件

Component或COM组件，是微软提出的一套通用二进制标准，遵循此标准的程序称之为组件，可以被其他程序调用。组件之前，dll等库的开发十分不便：1、库升级后可能无法向后兼容，因此用户不得不为旧软件保留旧版本的库，因此会有lib1.dll、lib2.dll的现象，这种方式也会增加库的调用者的开发难度。2、各个二进制库使用的编译器可能不一样，编译器的标准中并未对C/C++生成的机器码做十分细致的限制，不同编译器生成的机器码并不相同，因此，如果使用了不同的编译器将无法互相调用，库的提供者不得不将源码开源或使用多个版本的编译器来解决调用问题。COM组件定义了一系列的标准规范，利用其API实现这些规范即可成为通用组件，避免了上述问题。另外，COM组件不仅局限于C/C++，而是适用于所有遵循二进制规范的Native语言。