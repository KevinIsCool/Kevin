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

###简介
该站点内的这系列针对创建汇编代码的汇编教程，旨在让你为创建自己的汇编代码和Shellcode做好准备。非常期待你的代码被包含在“Project Shellcode Development Framework”中。

Windows Shellcode和Linux Shellcode之间有何区别？    
[http://www.vividmachines.com/shellcode/shellcode.html](http://www.vividmachines.com/shellcode/shellcode.html)

与Windows不同的是，Linux提供一种直接的方式与内核交互：通过int 0x80接口。完整的Linux系统调用表可以在[http://www.informatik.htw-dresden.de/~beck/ASM/syscall_list.html](http://www.informatik.htw-dresden.de/~beck/ASM/syscall_list.html)找到。另一方面，Windows没有直接的内核接口，与系统交互需要从一个DLL（动态链接库）中加载所需例程的地址。