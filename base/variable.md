变量提升
===========
 思考
-----
```javascript
console.log(test); // undefined
var test = true;
console.log(test); // true
```
##### 相当于

```javascript
var test;
console.log(test); // undefined
test = true;
console.log(test); // true
```
在一段JS代码拿过来真正一句一句运行之前，浏览器已经做了一些"准备工作"，其中就包括对变量的声明，
而不是赋值。变量赋值是在赋值语句执行的时候进行的。

原因
-----
变量提升的根本原因是**变量声明**与**赋值的分离**，
如例子 var test = true; 这个代码是分两步进行的。首先是 var test 这一部分的变量声明，
**这个过程是在代码编译时进行的。**
然后是 test = 2; 这一部分的变量赋值，**这个过程是在代码执行时进行的**。

###在"准备工作"中完成了哪些工作：

1、变量、函数表达 - 变量声明，默认赋值为undefined

2、this - 赋值

3、函数声明 - 赋值

这三种数据的准备情况我们称之为"执行上下文"