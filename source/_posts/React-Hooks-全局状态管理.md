---
title: React Hooks 全局状态管理
catalog: true
date: 2020-03-12 16:47:51
subtitle:
header-img:
tags:
- Skill
- Notes
- React
---
今天很开心，完成了一个简易的全局状态管理，记录一下自己的心路历程。

从上个项目开始，数据的流动变得无序且复杂了起来，
尝试使用Redux，因为操作比自己props数据还繁琐，放弃 =。=，
经历了一个项目迭代的折磨后，终于下定决心要使用全局的数据流管理。

于是想找个简易的方案，不想使用框架
百度过后发现 useContext + useReducer 可以实现，
但是自己手写的话会不会不成熟，后面问题太多怎么办，果然人类的欲望是前进的动力。

有没有轻量级的状态管理工具呢？

首先想到的是大佬们说过的Mobx，浏览了文档发现确实比Redux要简单。

但问题又来了，

这个项目使用的是React Hooks进行开发，可Mobx文档根本没看到Hooks语法的影子，
不过功夫不负有心人，一下午的功夫，我终于找到了Mobx兼容Hooks的官方文档，
https://mobx-react.js.org/recipes-migration
成功的让我放弃了emmmm
全英文文档看着头痛，时间也不太够了（加油补英语吧）。

又回到了 useContext + useReducer ，
安慰自己想想，其实自己需要全局变量的地方并不会很多，
所以自己手写没准才是最佳方案。

看似复杂其实拆解之后也很好理解。
useContext 传递上下文
useReducer 改变状态
用useContext将useReducer改变状态的方法传递过去就行
思路就是这么简单，理解了这两个 Hooks Api 后，多写几遍就熟悉了。

===
demo
===

最近重构项目又用Redux搞了一套，发现immer真好用！




