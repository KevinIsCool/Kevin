---
layout: post
title: Shellcode Tutorial
logo: 
category: tech
tags:
- Shellcode Tutorial
- Translation
excerpt: Hangzhou
---
**这一系列的教程，翻译自:[http://www.projectshellcode.com](http://www.projectshellcode.com)**    
**之所以想翻译这些文章，一是网上的翻译不是很好，二是方便大家学习，发扬极客精神。**    
**翻译不足的地方，请见谅！**

以下是关于**“Shellcode：从入门到精通”**的教程，这些教程会不断的进行更新，所以请确保你所看到的是最终的版本。

>[Shellcode Tutorial 1: Introduction and Tools Setup]()    
    对Shellcode进行一个简单的介绍，然后一步一步的搭建你自己的开发环境。

>[Shellcode Tutorial 2: My First Simple Shellcode]()    
    创建和测试一个简单的Shellcode。

>[Shellcode Tutorial 3: Windows Command Execution Shellcode]()    
    定义和定位一个字符串常量,并使用它来创建一个新的具有管理员权限的Windows用户。

>[Shellcode Tutorial 4: Message Box Shellcode]()    
    教你如何加载库，调用简单的函数以及如何执行它们。

>[Shellcode Tutorial 5: Function Hash Generation]()    
    定义和使用常量、更为复杂的函数，生成函数hash以及对OllyDbg进行简单的介绍。

>[Shellcode Tutorial 6: Dynamic Shellcode]()    
    动态定位Kernel32和函数地址。不再是硬编码地址！

>[Shellcode Tutorial 7: Introduction to Sockets - Portbind Shellcode]()    
    动态Shellcode：加载ws2_32.dll，创建一个给远程用户提供命令窗口的监听端口。

>[Shellcode Tutorial 8: Introduction to Networking - Connectback Shellcode]()    
    动态Shellcode：初始化一个反向链接，然后将它们连接到被破坏的系统的命令窗口。

>[Shellcode Tutorial 9: Generating Shellcode Using Metasploit]()    
    使用Metasploit Exploit框架的Web接口和msfpayload命令，针对不同格式的平台生成各种各样的Shellcode。