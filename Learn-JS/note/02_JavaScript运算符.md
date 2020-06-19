## 内容概述

## 1 算术运算符



```js
    var num1 = 20;
    var num2 = 4;
    var str1 = 'Hello';
    var str2 = 'World!';

    // 1. + - * / %
    console.log(+num1);
    console.log(num1 + num2);
    console.log(str1 + num1);
    console.log(str1 + str2);
    console.log(num1 - num2);
    console.log(num1 * num2);
    console.log(num1 / num2);
    console.log(num1 % num2);

    // 2. ++ --
    // 2.1 自增 
    var n1 = 100;
    n1++; // ++后置 101
    // ++n1; // ++前置 101
    console.log(n1); // 101

    // 2.2 自减
    var n2 = 100;
    n2--; // --前置 99
    // --n2; // --后置 99
    console.log(n2); // 99

    // 2.3 前置和后置的区别: 参与运算时
    var num = 100;
    // num++: 先使用, 再+1
    // ++num: 先+1, 再使用
    // result = num++ + 10; // 110
    result = ++num + 10; // 111
    console.log(result);

    // 练习
    var a = 10;
    var b;

    // b = 10 + 11 = 21
    // b = a++ + a++;
    // console.log(b); // 21

    // b = 10 + 12 = 22
    // b = a++ + ++a;
    // console.log(b); // 22

    // b = 11 + 11 = 22
    // b = ++a + a++;
    // console.log(b); // 22

    // b = 11 + 12 = 23
    b = ++a + ++a;
    console.log(b); // 23
```



## 2 赋值运算符

```js
    var num1 = 20;
    var num2 = 4;

    // num1 += num2; // 24
    // num1 -= num2; // 16
    // num1 *= num2; // 80
    // num1 /= num2; // 5
    num1 %= num2; // 0
    console.log(num1);
```



## 3 关系运算符

```js
    var num1 = 20;
    var num2 = 4;

    console.log(num1 == num2); // false
    console.log(num1 != num2); // true
    console.log(num1 > num2);  // true
    console.log(num1 < num2);  // false
    console.log(num1 >= num2); // true
    console.log(num1 <= num2); // false
```

### [JavaScript中的相等性判断](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Equality_comparisons_and_sameness)



```js
    // 1. 非严格相等 == 会进行隐式转换
    // string -> number 
    var num1 = 123;
    var str1 = '123';
    console.log(num1 == str1); // true

    // string -> number, boolean -> number
    var flag = true; // 1
    var str2 = 'true'; // NaN
    console.log(flag == str2); // false

    // 2. 严格相等 === 数据相等, 类型相等
    console.log(num1 === str1); // false
    console.log(flag === str2); // false

    // 3. != 会进行隐式转换
    console.log(num1 != str1); // false
    console.log(flag != str2); // true

    // 4. !== 
    console.log(num1 !== str1); // true
    console.log(flag !== str2); // true
```



## 4 逻辑运算符

- 与 &&
- 或 || 
- 非 !



```js
    var info = {
      name: 'yanlt',
      age: '23',

      // eat: function() {
      //   console.log('eating');
      // }
    }

    // 1. 与运算特殊用法
    // if (info.eat) {
    //   info.eat();
    // }

    // 短路与: 有一个条件为 false, 后续判断不再执行
    info.eat && info.eat();

    console.log('----------------');

    // 2. 或运算特殊用法
    // 短路或: 有一个条件为true, 后续判断不再执行
    var message = info.height || info.name || info.age;
    console.log(message); 
```

