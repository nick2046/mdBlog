## JavaScript Hoisting
在JavaScript中，一个变量名进入作用域的方式有4种：
```txt
1、Language-defined：所有的作用域默认都会给出 this 和 arguments 两个变量名;
2、Formal parameters（形参）：函数有形参，形参会添加到函数的作用域中;
3、Function declarations（函数声明）：如 function foo() {};
4、Variable declarations（变量声明）：如 var foo。
```
函数声明和变量声明总是会被移动（即hoist）到它们所在的作用域的顶部（这对你是透明的）。  
至于Language-defined和形参，显然，它们已经在顶部了。
#### 而变量的解析顺序（优先级），与变量进入作用域的4种方式的顺序一致。
1.我是变量声明，我会被提升在作用域顶端！
```js
var a;
```
2.我是变量定义，我的声明部分会被提升，赋值部分不会被提升！
```txt
var b = 'test';
```
3.我是函数定义，或者叫我函数表达式。其实我就是变量定义，只不过恰好被赋值的类型是函数，所以也只提升变量名，不提升函数值！
```txt
var c = function() {
    console.log('test');
}
```
4.我是函数声明，所以我全部被提升了，包括函数名和函数体。另外，我的优先级比变量声明要高，名字和我相同的变量声明会被忽略！
```txt
function d() {
    console.log('test');
}
```
