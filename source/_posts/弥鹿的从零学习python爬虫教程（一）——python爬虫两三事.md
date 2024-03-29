---
title: 弥鹿的从零学习python爬虫教程（一）——python爬虫两三事
date: 2020-06-26 02:07:21
tags: Python爬虫教程
---

从这篇文章开始，我将出一个《弥鹿的从零学习python爬虫教程》系列专栏，这是专栏的第一篇文章“python爬虫两三事”，简要介绍一下python爬虫的相关知识。话不多说，我们开始吧！

<!--more-->

##### 学习python爬虫你需要：

- python运行环境
- chrome浏览器

这两个是python爬虫学习的必备品哦，以后的章节就不再赘述了！

---



> **网络爬虫**（web crawler），也叫网络蜘蛛（spider）、自动索引程序（automatic indexer），是一种用来自动浏览万维网的网络机器人。其目的一般为编纂网络索引。
>
> <p align="right">——维基百科</p>

## 简谈爬虫与Python爬虫

虽然维基百科上把爬虫的目的概括为编纂网络索引，但大家都知道，爬虫的作用目前已经远远超过此范围。我们想批量获得网站上的信息、下载一些感兴趣的内容、与网站进行大规模的交互、甚至是刷票、抢票软件里都少不了爬虫的影子，可以说这是我们畅游互联网期间的一项有利工具！

说起爬虫，我们需要谈谈它的历史。爬虫最早期的形式不是像现在一样对互联网中的各种内容进行获取，而只是一个简单的索引工具。在互联网的早期发展中，由于互联网中的文件数量过多，查询起来极为不便，一种对网络中的文件进行索引供用户查询的“**电脑机器人**”便应运而生，这便是爬虫的前身。之后这种索引工具慢慢发展成了我们现在熟知的搜索引擎，所以我们可以说，搜索引擎是一种最为常用的爬虫工具。

那么你可能会问，C能写爬虫，Java能写爬虫，但为什么我们提到爬虫首先想到的就是Python呢？回答也很简单，因为它太简便了！Python中爬虫包的使用和其中各种API的定义都相当简洁与清晰，几行代码便可以实现一个简单的爬虫程序，而相同的工作放到C和Java中，你可能要编写几十行代码。还有一点，现在网络上关于Python爬虫的教程相当之多，你遇到的问题基本上都可以得到其他人的答案。而使用其他语言的话，学习过程中的诸多问题很可能得不到及时的帮助，如果没有探索精神的话，慢慢你就会学不下去了！

## 网站中的robots.txt

不知道你是不是第一次听说这个小东西，但我想告诉你，它很容易理解，其本质就是一张网站给爬虫程序的“禁令”，里面写着的内容都是不允许爬虫程序访问的页面。你可以试试看一下淘宝限制爬取的内容[https://www.taobao.com/robots.txt](https://www.taobao.com/robots.txt)，是不是下面这样的：

```
User-agent: Baiduspider
Disallow: /

User-agent: baiduspider
Disallow: /
```

试一试理解一下其中的含义，有没有猜到，文件的意思是限制百度搜索引擎爬取该域名下的所有文件。其实这件事还要追溯到2008年9月8日，淘宝网正式宣布封杀百度爬虫。淘宝表示，此举是为了保护淘宝用户的利益，可以杜绝不法商家利用竞价排名、搜索优化等手段骗取消费者信任，并对优秀卖家进行鼓励。

咳咳，说的有点偏。言归正传，是不是很神奇？一个.txt格式的文件居然能起到限制自动搜索程序访问的作用！但实际上不是这样，robots.txt的限制仅仅是道德层面的，也就是说，爬虫完全可以不顾robots.txt内的规定对其中限制的网页内容进行爬取。只是因为各个搜索引擎及大多规范的爬虫程序都严格遵守着这个规定，才有了现在相对稳定的爬虫环境。

***如果你不想让你的爬虫程序涉及到法律相关的问题，请不要爬取robots.txt限制的内容！***

## 爬虫的风险

现在因为爬虫而违法的案例屡见不鲜，如果没有较强的法律意识，很容易因为爬虫或者其他黑客行为获得“破坏计算机信息系统罪”。那么如何保证自己的爬虫程序是合法的呢？我总结了一下，主要有以下几点：

1. 爬虫严格遵守网站robots.txt规定
2. 爬虫不涉及用户隐私
3. 不能影响站点正常运行（高频度大量访问站点轻则被禁IP，重则被当作DDoS严肃处理）
4. 不能影响站点正常经营（把别人数据库的东西都搬到自己的网站并且与对方竞争，也是会被严肃处理的）
5. 不能以盈利为目的

做到上述这些，同时你的爬虫程序是以学习为目的的，我想不会出太大的问题哦。



关于爬虫的一点点闲谈就说到这，从下一期开始我们将进入正式的学习，准备好你的python环境和chrome浏览器，我们准备开始！



*弥鹿lum*

*版权所有，未经许可，禁止转载*