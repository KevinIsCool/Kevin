---
layout: post
title: Shellcode Tutorial 1 - Introduction and Tools Setup
logo: 
category: tech
tags:
- Shellcode Tutorial
- Translation
excerpt: Hangzhou
---

**翻译自：[Shellcode Tutorial 1: Introduction and Tools Setup](http://www.projectshellcode.com/node/17)**    

##0x01 简介
该站点内的这系列针对创建汇编代码的汇编教程，旨在让你为创建自己的汇编代码和Shellcode做好准备。非常期待你的代码被包含在“Project Shellcode Development Framework”中。    

**Windows Shellcode和Linux Shellcode之间有何区别？**    
[http://www.vividmachines.com/shellcode/shellcode.html](http://www.vividmachines.com/shellcode/shellcode.html)    

与Windows不同的是，Linux提供一种直接的方式与内核交互：通过int 0x80接口。完整的Linux系统调用表可以在[http://www.informatik.htw-dresden.de/~beck/ASM/syscall_list.html](http://www.informatik.htw-dresden.de/~beck/ASM/syscall_list.html)找到。另一方面，Windows没有直接的内核接口，与系统交互需要从一个DLL（动态链接库）中加载所需例程的地址。这两个系统相比，最大的不同点是：Windows中的函数地址随着系统版本的不同而不同，而int 0x80系统调用则不会。Windows程序员之所以这么做是因为通过这种方式他们可以很简单的根据需求改变系统内核。与之相反的是，对于所有内核层的函数，Linux已经为它们确定了数字系统，所以如果试着去改变它们，估计会多出无数愤怒的程序员以及无数的无用代码。    

**所以，对于Windows怎么办？我该如何找到我所需的DLL中函数的地址？这些地址会随着每一次服务包的升级而改变么？**    
[http://www.vividmachines.com/shellcode/shellcode.html](http://www.vividmachines.com/shellcode/shellcode.html)    

有很多的方法可以找到你的Shellcode中所需的函数的地址。其中有两种方法是：运行时定位函数地址和使用硬编码。该教程更倾向于讨论硬编码的方法。唯一确定需要映射进Shellcode地址空间的DLL是kernel32.dll。该DLL中导出了LoadLibrary 和GetProcAddress函数，这两个函数可以获得那些任何可以映射进exploits进程空间的函数地址。这种方法有一个问题，（函数）地址的偏移量会随着Windows新版本的更新而改变（服务包，补丁等）。所以，如果你用这种方法，你的Shellcode将只能运行在特定版本的Windows之上。     

动态查找函数地址将在之后的教程中讲解。      
**让我们开始配置开发环境吧！**