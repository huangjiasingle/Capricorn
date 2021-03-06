---
layout: blog
title: 'Flask源码剖析（二十）：总结'
date: 2017-09-22 23:53:04
categories: flask
tags: flask
lead_text: '总结'
---

## 一. 总结
Flask框架是个微框架，用于熟悉Python的基础语法，怎么进行源码分析学习,学习一个框架是怎么实现等等都是很有帮助的。

## 二. 分析
1. 语法参考
- 在解析flask源码过程中，就当是重新复习一下python的基础语法，另外，可再翻一遍[Python学习手册(第4版) 中文版]()，开卷有益。

2. 源码分析
- 在读别人的源码之前，先了解这个程序的用途，简单过一遍，计算下代码量，心里有个底
- 选取恰当的分析源码的工具
- 找到这个程序的执行起始点，从上往下分析，列出程序的调用链
- 解析这个程序的大体框架和设计模式，如果是单纯了解程序的工作机制，那么需要从大局出发，整体把握系统架构和设计模式即可，不用了解每个细节
- 如果要深入理解程序的运作，那么在整体把握系统架构后，需要解析每个代码的运作细节，熟悉程序的执行起始点
- 有需要的话，画出程序中的各个调用链

3. 行为分析
- 源码分析是个耗时久，且不太可能看得见成效的工作，要养成定时定量去看，不要靠着一腔热血就盲目跳坑
- 理性看待每件事背后的动机，事情的起源都必有其动机，基于什么宗旨，所要达成的目的
- 良好的行为习惯和思维方式，比努力更加重要，其他的只剩下坚持了

## 三. 补充
参考资料：
1. [flask 源码解析](http://cizixs.com/2017/01/10/flask-insight-introduction)
2. [Python 魔术方法指南](http://pycoders-weekly-chinese.readthedocs.io/en/latest/issue6/a-guide-to-pythons-magic-methods.html)