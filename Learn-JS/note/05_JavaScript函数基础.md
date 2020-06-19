# 内容概述

## 函数的定义和调用

```js
    function printInfo() {
      console.log('yanglt');
      console.log(18);
      console.log(1.88);
    }
    printInfo();
```



## 函数的参数

```js
    function printInfo(name, age, height) {
      console.log(name);
      console.log(age);
      console.log(height);
    }
    printInfo('yanglt', 18, 1.88)
```



## 函数的返回值

- 注意事项

  - 使用return关键字来返回结果
  - 一旦在函数中执行return操作, 那么当前函数会终止
  - 如果函数中没有return语句, 那么函数有默认的返回值: undefined
  - 如果函数使用return语句, 但是return后面没有跟任何值, 那么函数的返回值也是: undefined

  

```js
    function sum(num1, num2) {
      var result = num1 + num2;
      console.log(result);
      return result;
    }   
    var sum = sum(10, 20);
    console.log(sum);

    //  一旦在函数中执行return操作, 那么当前函数会终止
    // 如果函数使用return语句, 但是return后面没有跟任何值, 那么函数的返回值是: undefined
    function test01() {
      console.log(1);
      console.log(2);
      return;
      console.log(3);
      console.log(4);
    }
    var res01 = test01();
    console.log(res01);

    // 如果函数中没有return语句, 那么函数有默认的返回值: undefined
    function test02() {
      console.log('a');
      console.log('b');
    }
    var res02 = test02();
    console.log(res02);
```



## arguments参数

- 默认情况下，arguments对象是所有(非箭头)函数中都可用的局部变量
- 该对象中存放着所有的调用者传入的参数，从0位置开始，依次存放
- arguments变量的类型是一个object类型，不是一个数组，但是和数组的用法看起来很相似
- 如果调用者传入的参数多于函数接收的参数，可以通过arguments去获取所有的参数

```js
    function sum() {
      var total = 0;
      for (var i = 0; i < arguments.length; i++) {
        total += arguments[i];
      }
      return total;
    }

    console.log(sum(1, 2, 3, 4, 5));
```



## 变量作用域

```js
    // 变量作用域: 变量在哪个范围可以被使用, 这个范围就是变量的作用域
    // 1.块级作用域: 在JavaScript(ES5)里面没有块级作用域
    {
      var age = 18;

      // ES6有块级作用域, 使用let关键字,
      // let age = 18; 
    }
    console.log(age); // 18

    // 2.函数作用域: 函数有自己的作用域
    function test() {
      // 局部变量
      var height = 1.88;
      // var name = 'kobe';
      console.log(name);
    }
    // console.log(height); // undefinded

    // 全局变量
    var name = 'yanglt';
    test();

    // 结论一: 在全局默认不可访问局部变量
    // console.log(height);

    // 结论二: 在函数中, 访问一个变量时, 会优先查找自己的局部变量, 如果没有找到, 会去找全局变量
```



## 函数表达式写法

```js
    // 1.函数的定义方式一: 函数的声明写法
    // name属性的值: 函数的名字
    function test01() {
      console.log('test01被调用');
    }
    test01();

    // 2.函数的定义方式二: 函数表达式
    // 2.1 命名函数表达式
    // name属性的值: 函数的名字
    var abc = function test02() {
      console.log('test02被调用');
    }
    abc();

    // 2.2 匿名函数表达式
    // name属性的值: 赋值的变量的名字
    var test03 = function() {
      console.log('test03被调用');
    }
    test03();

    // 3.函数都有一个属性: name
    console.log(test01.name);
    console.log(abc.name);
    console.log(test03.name);
```



## 立即执行函数(Immediately-Invoked Function Expression)

```js
    // 1.JavaScript不允许直接在一个函数的声明后跟()执行这个函数
    // 1.1 下面的函数不能立即执行
    function test() {
      console.log('test被调用');
    }
    test();

    // 1.2 改进一: 给函数整体包一个小括号
    // (function test01() {
    //   console.log('test01被调用');
    // })();
    // 特点: 执行后立即销毁, 所以test01这个名字没有意义
    // test01(); 报错
    (function() {
      console.log('改进后test01被调用');
    })

    // 1.3 改进二: 将函数和执行的()一起包一个小括号
    // (function test02() {
    //   console.log('test02被调用');
    // }())

    (function() {
      console.log('改进后test02被调用');
    }())

    // 2.匿名函数表达式可以在后面跟()立即执行函数
    var demo = function() {
      console.log('demo被调用');
    }();
    console.log(demo); // undefined
```



## 值传递和引用传递

```js
    // 1.值传递
    function test(name) {
      console.log(1, name); // 'yanglt'
      name = 'kobe';
      console.log(2, name); // 'kobe'
    }

    var temp = 'yanglt';
    test(temp);
    console.log(3, temp); // 'yanglt'

    // 2.引用传递
    function test02(arr) {
      arr[0] = '99';
      console.log(arr); // [99, 2, 3, 4, 5]
    }
    var arr = [1, 2, 3, 4, 5];
    test02(arr);
    console.log(arr); // [99, 2, 3, 4, 5]
```

