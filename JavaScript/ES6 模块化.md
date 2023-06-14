# ES6 模块化

- AMD 和 CMD 适用于浏览器端的 JS 模块化

- CommonJS 适用于服务器端的 JS 模块化
  - CommonJS （Node.js 的标准）
- ES6 模块化规范
  1. 每个 JS 文件都是一个独立的模块
  2. 导入其他模块成员使用 import 关键字
  3. 向外共享模块成员使用 export 关键字

## 在 Node.js 中体验 ES5 模块化

```
// 新建包管理文件 package.json
npm init -y 
// 在根节点中添加模块化
"type": "module"
```

## 基本语法

1. 默认导出和默认导入(注意事项： export default 只能使用一次)

   1. 默认导出 export default 默认导出的成员对象（导出的是一个对象）
   2. 默认导入 import 接收名称 from '模块.js'（接受上面导出的对象的名称）

2. 按需导出和按需导入

   1. 按需导出 export 成员名称
   2. 按需导入 import {} from 

   注意事项：

   1. 模块中可以多次按需导出
   2. 按需导入的成员名称必须和按需导出的名称保持一致
   3. 按需导入时，可以使用as关键字进行重命名
   4. 按需导入可以和默认导入一起使用（import info）

3. 直接导入并执行模块中的代码 直接import模块

# Promise

## 回调地狱

多层回调函数相互嵌套，形成了回调地狱。

tips: 什么是回调函数（在某些事情结束之后执行的函数）

缺点：代码耦合性太强，难以维护；大量冗余代码互相嵌套，代码的可读性变差。

## Promise 的基本概念

1. Promise 是一个构造函数 const p = new Promise()
2. new 出来的 Promise 实例对象，代表一个异步操作
3. 原型对象 Promise.prototype 上包含一个 .then() 方法
4. .then 预先指定成功和失败的回调函数
   1. p.then(result => {}, error => {}) 成功是必选的，失败是可选的

如何按顺序输出？

**.then 方法的特性**：

- 如果上一个 .then()方法中返回了一个新的Promise实例对象，则可以通过下一个.then()继续进行处理。
- 通过这样的链式调用，可以解决回调地狱的问题

**通过 .catch 捕获错误**

**Promise.all()** 会发起并行的 Promise 异步操作了，等所有的异步操作全部结束后才会执行下一步的.then操作

**Promise.race()** 会发起并行的Promise异步操作，只要任何一个异步操作完成，就立即执行下一步的.then操作

**Promise 异步操作的结果，可以用 resolve 或 reject 回调函数进行处理**

```javascript
if(err) return reject(err)
resolve(dataStr)
```

## async / awit

async / awit 是 ES8 引入的新语法，用来简化 Promise 异步操作

async / awit出现之前，开发者只能通过.then()方法链式处理 Promise() 异步操作

在 async 方法中，第一个 await 之前代码会同步执行，await 之后的代码会异步执行

