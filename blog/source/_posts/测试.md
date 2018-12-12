---
title: ES6 常用的数组方法
toc: true
date: 2018-12-12 14:11:23
tags:
---
---
###  ES5中常用的10中数组遍历方法
- 1、原始的for循环语句
- 2、Array.prototype.forEach(each, item,arr)数组对象内置方法
- 3、Array.prototype.map(each, item,arr)数组对象内置方法
- 4、Array.prototype.filter(each, item,arr)数组对象内置方法
- 5、Array.prototype.reduce数组对象内置方法
- 6、Array.prototype.some(each, item,arr)数组对象内置方法: 只要有满足条件的就返回true，且只要发现有通过的项就不再继续遍历
- 7、Array.prototype.every(each, item,arr)数组对象内置方法：每一项都满足条件才会返回true，且只要发现有没有通过的项就不再继续遍历
- 8、Array.prototype.indexOf(item)数组对象内置方法: 返回数组中第一个item的索引
- 9、Array.prototype.lastIndexOf(item)数组对象内置方法: 返回数组中最后一个item的索引
- 10、for...in循环语句

---
### ES6中新增了一种
- for...of循环语句：看着有点像for...in语句，但是和for...in语句不同的是它不可以循环对象，只能循环数组。

```
var a = [1,2,3];
for(var value of a){
  console.log(value)  // 结果依次为1，2，3
}
```


##### 下面是示例数据
```
const temporaryArray = [6,7,4,3,1,2];

const temporaryObject = {
    a: 1,
    b: 2,
    c: 3,
};

const objectArray = [
    {
        id: 1,
        name: 'bd',
    },
    {
        id: 2,
        name: 'ba',
    },
    {
        id: 3,
        name: 'cd',
    },
]

```

### reduce(callBack, initValue)方法：
  对数组中的元素应用相应的运算，并且返回最终的结果，参数有2个，第一个是一个函数，规定运算方式，这个函数共有四个参数(accumulator, currentValue, currentIndex, array),第二个是初始值，如果不传的话默认从数组的第一个元素开始运算，如果传了的话默认运算的第一个元素就是传入的initValue。

- accumulator: 累积器，用来存放上一次迭代之后运算的结果。
- currentValue: 当前值
- currentIndex当前索引值，
- array当前数组


```
// 不传第二个参数initValue
const result = temporaryArray.reduce( function(accumulator, currVal, curIndex, arr){
    return  accumulator + currVal;
});
// 23

// 传第二个参数initValue
const _result = temporaryArray.reduce( function(accumulator, currVal, curIndex, arr){
    return  accumulator + currVal;
}, 7);
// 30
```

