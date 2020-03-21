
ES6新特性回顾

> https://juejin.im/entry/5dfa5d8ff265da33c24ff41b


### 1、let、const、var

在es6开发中  `var`主要负责定义全局变量 ，因为全局作用域定义的变量会自动挂载到window对象下面

首先需要理解几大概念
- 变量提升：变量定义之前就可访问
- 暂时死区  外部定义后，块内let/const定义前面访问报错区域
- 块作用域类似C语言的大括号内结尾局部作用域

主要区别

|  | var | let | const |
|--|--|--|--|--|
| 变量提升 | 1 |  |  |
| 全局变量 | 1 |  |  |
| 重复声明 | 1 |  |  |
| 重新赋值 | 1 | 1 |  |
| 暂时死区 |  | 1 | 1 |
| 块作用域 |  | 1 | 1 |
| 只声明不初始化 | 1 | 1 |  |

从区别衍生的优缺点 

#### var

- 可以定义全局变量
- 只存在一般作用域和函数作用域，其他情况（比如if，for内定义的变量存在变量提升）
- 可以重新赋值，对代码健壮性不是很友好

问题：

- 内层变量可能覆盖外层变量
- 用来计数的循环变量泄露为全局变量

#### let

除了全局变量，一般用于替代`var`

#### const

- const 声明之后必须马上赋值，否则会报错
- 且赋值之后不可修改，推荐用于固定变量
- 常量、声明匿名函数、箭头函数的时候

### 2、类Class

es6之前，声明一个实例对象时，需要写一个构造函数

```js
function Person(name,age){
    this.name = name;
    this.age = age;
}
Person.prototype.information = function(){
    return 'my name'+this.name+'age' + this.age
}
```
class的写法

```js
class Persion{
    constructor(name , age){
        this.name = name;
        this.age = age;
    }
    information(){
       return 'my name'+this.name+'age' + this.age
    }
}

```
### 3、箭头函数

没有自己的this、argument、super或new.target

更简单的说箭头函数属于变量方法，并不集成子Function对象

主要用来替代匿名函数，或者一些简单函数

### 4、函数默认值
```js
const config = (data = 0)=>{ return data}
```

### 5、模板字符串
```js
const config = (data = 0)=>{ return `${data}数据`}
```

### 6、结构赋值

a、b变量对换
```js
let a =3,b =5;
[a,b] = [b,a]
```

将属性值从对象、数组中取出，赋值其他变量

### 7、模块化

ES6之前的模块化，js并没有模块化概念，只有社区制定的Commonjs和AMD之类的规则

es6 则可以使用 `import`

### 8、扩展操作符


```js
let a= [1,2,3,4]
const fn= (a,b,c,d)=>{return a+b+c+d}
fn(...a)
```

注意在对象身上的使用

### 9、对象属性简写

```js
let a= 1;
let b= 2;
let c = 3;
let obj ={a,b,c};
```

### 10、异步操作promise
常见用法
```js
const pro = ()=>{
    return new Promise((resolve,reject)=>{
        resolve('成功');
        reject("失败")
    })
}

```

### 11、for...of

在可迭代对象中，创建一个迭代循环，调用自定义迭代钩子，并为每个不同属性的值执行语句

### 12、Symbol数据类型

一种基本的数据类型该类型具有静态属性和静态方法。它的属性会暴露几个内建的成员对象；它的静态方法会暴露全局的symbol注册，类似于内建对象类，但作为构造函数来说它并不完整因为她并不完整  因为不支持 `new Symbol()`




### 13、迭代器、生成器

一种迭代机制，为各种不同的数据结构提够统一的访问机制。任何数据结构只要内部有接口 就可以依次完成迭代操作。


### 14、Set和WeakSet类型

Set只允许存任何类型的唯一值（最简单的去重）

WeakSet是特殊的Set
- 只能存放对象引用，不能存放值，而set对象都可以。
- WeakSet存储的对象值都是被弱引用的，如果没有被引用则会被当做垃圾处理回收，所以无法被枚举


### 15、proxy/Reflect

proxy主要用于定义基本操作的自定义行为

Reflect是一个内置对象提供拦截JavaScript的操作方法，与proxy的方法相同。

### 16、Regex对象的扩充
### 17、Math对象的扩展
### 18、Array对象的扩展
### 19、ES7
### 20、模板字符串

### 5、模板字符串
### 5、模板字符串


