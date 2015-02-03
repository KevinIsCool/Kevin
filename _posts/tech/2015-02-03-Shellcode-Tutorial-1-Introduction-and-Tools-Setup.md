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

