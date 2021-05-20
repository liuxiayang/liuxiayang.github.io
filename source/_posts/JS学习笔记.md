---
title: JS学习笔记
catalog: true
date: 2019-06-10 14:47:51
subtitle:
header-img:
tags:
- Skill
---

### Reduce
语法

    arr.reduce(callback,[initialValue])

reduce 为数组中的每一个元素依次执行回调函数，不包括数组中被删除或从未被赋值的元素，
接受四个参数：初始值（或者上一次回调函数的返回值），当前元素值，当前索引，调用 reduce 的数组。

    callback （执行数组中每个值的函数，包含四个参数）

        1、previousValue （上一次调用回调返回的值，或者是提供的初始值（initialValue））
        2、currentValue （数组中当前被处理的元素）
        3、index （当前元素在数组中的索引）
        4、array （调用 reduce 的数组）

    initialValue （作为第一次调用 callback 的第一个参数。）

例子

    var  arr = [1, 2, 3, 4];
    var sum = arr.reduce(function(prev, cur, index, arr) {
        console.log(prev, cur, index);
        return prev + cur;
    }，0) //注意这里设置了初始值
    console.log(arr, sum);

>打印结果：
 0 1 0
 1 2 1
 3 3 2
 6 4 3
>[1, 2, 3, 4] 10

简单用法:数组求和，求乘积。
高级用法:
（1）计算数组中每个元素出现的次数
（2）数组去重
（3）将二维数组转化为一维
（4）对象里的属性求和

    var result = [
        {
            subject: 'math',
            score: 10
        },
        {
            subject: 'chinese',
            score: 20
        },
        {
            subject: 'english',
            score: 30
        }
    ];

    var sum = result.reduce(function(prev, cur) {
        return cur.score + prev;
    }, 0);
    console.log(sum) //60

