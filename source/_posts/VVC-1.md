---
title: VVC(1)
date: 2025-03-20 02:19:44
tags:
---

VVC官方测试软件VTM代码分析
从可以下载VTM代码，本文的具体分析对象为VTM10.0
VTM的源码可以在source文件夹中找到，具体分成两部分App和Lib。App文件夹下包含了VTM的应用程序，即实现了编码器和解码器开始编解码过程后的具体行为，包括程序运行主函数。EncoderApp和DecoderApp下各有一个CMakeLists.txt用以编译，最后可得到两个可执行文件EncoderApp和DecoderApp分别作为编码器和解码器的功能调用接口。Lib文件夹中包含了各种编码器和解码器所需使用的功能库和数据结构。
进入EncoderApp文件夹中通过encmain.cpp可以具体研究编码器的行为逻辑，