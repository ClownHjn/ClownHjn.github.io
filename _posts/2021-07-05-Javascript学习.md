---

layout: post

title: javascript学习

date: 2021-07-05

tags: Javascript

---

## javascript

## 入门语法

### iterable

iterable类型集合可以通过新的for ... of 循环进行遍历

for ... of 循环时ES6新的语法

```javascript
'use strict'
var a = [1,2,3];
for (var x of a){
    console.log(x)
}
```

for ... in  实际遍历的是对象属性名称，一个Array数组实际上也是一个对象，它的每个元素的索引被视为一个属性。

```javascript
var = a ['a','b','c'];
a.name = 'helo';
for (var x in a){
    console.log(x); // '0','1','2','name'
}
```

#### forEach

它接收一个函数，每次迭代就自动回调该函数

```javascript
'use strict'
var a = ['A','B','C']
a.forEach(function(element,index,array){
    // element: 指向当前元素的值
    // index: 指向当前索引
    // array: 指向Array对象本身
})
```

PS: forEach 是ES5.1标准引入

##### Set

`Set`与`Array`类似，但`Set`没有索引，因此回调函数的前两个参数都是元素本身

```javascript
var s = new Set(['A', 'B', 'C']);
s.forEach(function (element, sameElement, set) {
    console.log(element);
});
```

##### Map

`Map`的回调函数参数依次为`value`、`key`和`map`本身

```javascript
var m = new Map([[1, 'x'], [2, 'y'], [3, 'z']]);
m.forEach(function (value, key, map) {
    console.log(value);
});
```

## 函数

#### arguments

它只在函数内部起作用，并且永远指向当前函数的调用者传入的所有参数。`arguments`类似`Array`但它不是一个`Array`

```javascript
'use strict'
funciton foo(x){
    console.log('x=' +x ); //10
    for (var i=0; i<arguments.length; i++){
        console.log('arg' +i + '=' + arguments[i]); // 10,20,30
    }
}
foo(10,20,30);
```

常用于判断传入参数个数 pg

```javascript
function foo(a,b,c){
    if (arguments.length ===2){
        c = b;
        b = null;
    }
}
```

#### rest(ES6)

获取除了已定义参数a、b之外

```javascript
function foo(a,b, ...rest){
    console(rest);
}
```

