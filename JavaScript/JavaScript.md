# JavaScript

## 书写位置

- 行内
- 内部
- 外部

## 基本语法

```javascript
// 输出语法
document.write()
alert()
console.log()
// 输入语法
prompt() //显示一个对话框，提示用户输入文字

```

### 变量

let 变量名

变量可以更新值，但不能反复声明

变量命名规则：

1. 不能用关键字
2. 数字不能开头，变量只能由下划线、字母、数字和$组成
3. 字母严格区分大小写

规范：驼峰

## 数值类型

### 数组（Array）

let 数组名 = [ ]

### 常量（const）

const 变量名 =

### 数字类型（Number）

let 变量名 = 整数、小数、整数、负数

### 字符串（string）

推荐使用单引号

### 模板字符串

用来拼接字符串和变量

语法：``（反引号）

内容拼接变量时，用${}包住变量

### 布尔型、undefined 和 null

undefined 声明但未赋值

null 空值

typeof X / typeof(X)检测数据类型

## 类型转换

### 隐式转换

除了+，其他运算符都会把字符串转为数字

+“123” 转换为数字

### 显式转换

- Number()
- parseInt()只保留整数，不进行四舍五入
- parseFloat()可以保留小数

## 运算符

### 赋值运算符

+= / -= / *= / /= / %=

### 一元运算符

正负号

前置自增和后置自增的区别：

- 前置自增先自加再返回原值
- 后置自增先返回原值后自加 表达式先原值返回变量再自加1 变量比表达式大1

### 比较运算符

== 值是否相等

=== 值和类型是否都相等

### 逻辑运算符

&& 与

|| 或

！非

### 运算符优先级

1. （）
2. 一元 ！
3. 算数
4. 关系/比较
5. 相等
6. 逻辑  先 && 后 ||
7. 赋值

## 语句

### 分支语句

```javascript
// 单分支
if (codition) {
    code
}
// 双分支
if () {
    
}
else {
    
}
// 多分支
if () {
    
} else if () {
    
} else () {
    
}
// 三元运算符
条件? 满足条件执行的代码：不满足条件执行的代码
// switch
switch () {
    case value1:
    	code1
        break
    case value1:
    	code1
        break
    default:
    	code1
}
```

### 循环语句

```javascript
// while
while () {
    
}
// for 
for (变量起始值; 终止条件; 变量变化量) {
    
}
```

# ES6+ 新特性

## 作用域

### 局部作用域

函数内部变量，外部无法访问

let 和 const 声明的变量会产生块作用域，var 不会产生块作用域

### 全局作用域

全局声明的变量，其他函数均可访问

### 作用域链

作用域链本质：变量查找机制，当前作用域查不到则依次逐级查找父级作用域直到全局作用域

### 垃圾回收机制GC

内存不使用时被垃圾回收器自动回收

内存分配生命周期：

- 内存分配：
- 内存使用：
- 内存回收：

ps：

1. 全局变量一般不会回收
2. 一般情况下局部变量的值，不用了就会被回收

### 闭包

闭包：一个函数对周围状态的引用捆绑在一起，内层函数中访问其外层函数的作用域

闭包 = 内层函数 + 外层函数的变量

有什么用：封闭数据，提供操作，外部可以访问函数内部的变量，实现数据私有

注意事项： 内存泄漏

## 箭头函数

替代原本需要匿名函数的地方

### 基本语法

```javascript
const fn = () => {
    console.log(123)
}
fn()
```

只有一个形参的时候可以省略小括号

只有一行代码可以省略大括号和return

### 箭头函数参数

普通函数有 arguments 动态参数

箭头函数没有动态参数，但是有 ...args 剩余参数

### 箭头函数的 this

普通函数：this 谁调用，this 指向谁

箭头函数的 this 指向 window (原理不是调用，而是作用域链，指向上一层，因为箭头函数本身没有 this)

## 解构赋值

### 数组解构

基本语法：将数组单元值快速批量赋值给一系列变量

```javascript
const arr = [1, 2, 3]
cosnt [a, b, c] = [1, 2, 3]
// 交换变量
let a = 1
let b = 2;
// 这个分号必须加
[a, b] = [b, a]
```

变量多，单元值少——依次传递，未传递的值为 underfined

变量少，单元值多——用剩余函数处理、或者设置默认值

### 对象解构

解构属性和方法，变量名和属性名一样

结构 JSON 常用

```javascript
const {uname, age} = { uname: 'pink', age: 18}

const pig = [
    {
        uname: 'pink',
        age: 6
    }
] 
const [{ uname, age }] = pig

const pig = 
    {
        uname: 'pink',
        family: {
            father: 'father',
            mother: 'mother'
        }
    }
const { uname, family:{ father, mother }} = pig
```

## 构造函数

### 创建对象

1. 对象字面量
2. new Object
3. 构造函数

### 构造函数

```javascript
function Pig(name, age, gender) {
    this.name = name
    this.age = age
    this.gender = gender
}
```

### 实例成员  静态成员

实例化执行过程

1. 创建新空对象
2. 构造函数 this 指向新对象
3. 执行构造函数代码，修改 this，添加新的属性
4. 返回新对象 

实例对象的属性和方法属于实例成员

实例对象之间相互独立

构造函数的属性和方法称为静态成员

静态成员只能通过构造函数访问

静态成员的 this 指向构造函数

Object 方法 

1. Object.assign(对象，被复制对象)（常用于添加属性）

Array 

1. forEach 遍历数组 不返回数组
2. fliter 过滤数组 返回新数组
3. map 迭代数组 返回新数组
4. reduce 累计器 返回结果

## 原型

解决构造函数的内存浪费问题

利用原型对象实现方法共享

- 构造函数通过原型分配的函数是所有对象所共享的
- 每一个构造函数都有一个 prototype 属性，指向另一个对象
- 该对象可以挂载函数，对象实例化不会多次创建原型上函数
- 可以把不变的方法直接定义在 prototype  对象上实现内存节省
- 构造函数和原型对象中的 this 都指向实例化的对象

语法：构造函数.prototype.名称 = 方法

### constructor

重新指回原型对象的构造函数

在哪里：在原型对象里面，是原型对象的一个属性

作用：该属性指向该原型对象的构造函数

### 对象原型

```javascript
__proto__ [[prototype ]]
// 用来表明当前实例对象指向哪个原型对象 prototype

// 对象原型指向该构造函数的原型对象
function Star() {}
const ldh = new Star()
console.log(ldh.__proto__ === Star.prototype) // true

// 对象原型的 constructor 属性，指向创建该实例对象的构造函数

```

![image-20230608162839740](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20230608162839740.png)

### 原型继承

```javascript
const Person = {
	  head: 1
}
function Man() {
}
// 通过原型继承
Man.prototype = Person、
// 由于继承后覆盖了prototype，缺失了constructor属性，重新指回构造函数
Man.prototype.constructor = Man
const Pink = new Man()
console.log(Pink)
```

### 原型链

```javascript
function Person() {}
const zxw = new Person()
// 实例对象的对象原型指向构造函数的原型
console.log(zxw.__proto__ === Person.prototype) // true
// 构造函数的对象原型指向 Object 的原型（自定义的构造函数的构造函数是 Object）
console.log(Person.prototype.__proto__ === Object.prototype) // true
// instanceof 运算符用于检测构造函数的 prototype 属性是否出现在某个实例对象的原型链上
// (实例对象 instanceof 构造函数)
console.log(zxw instanceof Person) // true
console.log(zxw instanceof Object) // true
console.log(zxw instanceof Array)  // false
```

![image-20230608174000477](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20230608174000477.png)

![image-20230608174233140](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20230608174233140.png)