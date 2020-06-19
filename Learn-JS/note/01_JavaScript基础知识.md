# 内容概述

## 1 邂逅 JavaScript

### js代码编写位置

- 在html元素中直接执行JavaScript代码
- 书写到script标签中
- 从外部引入js文件



### 注意事项

- script 标签不能写成单标签
- script 标签省略了type属性
- 加载顺序
  - 作为html文档的一部分，js默认遵循html文档的加载顺序，即自上而下加载
  - 推荐将js代码和编写位置放在body子元素的最后一行
- JavaScript代码严格区分大小写



### 注释写法

```js

    // 1.js代码注释写法一: 单行注释

    /* 2.js代码注释写法二: 多行注释
    */ 
	
	// 3.js代码注释写法三: 文档注释
    /** 
     * 这是一个测试函数
     */ 
    function test() {

    }

    test();
```



### 浏览器交互方式

- 弹窗显示内容
  - alert()
  - 接收一个参数
- 在控制台打印
  - console.log()
  - 接收多个参数, 以逗号分隔
- DOM操作
- 接收用户输入
  - prompt()



## 2 变量

### 变量的定义方式

```js
var name = 'yanglt';

var age
age = 23;

var num1, num2, num3;
var numa = 1, num2 = 2;
```



### 变量的命名规则和规范

- 变量的命名规则
  - 第一个字符必须是一个字母, 下划线(_)或一个美元符号($)
  - 其他字符可以是字母, 下划线, 美元符号或数字
  - 不能使用关键字或保留字命名

- 变量的命名规范
  - 多个单词使用驼峰标识
  - 语义化命名
  - 赋值等号两边加空格
  - 语句结束加分号



### 变量练习

- 交换数字

```js
var num1 = 100, num2 = 200;

num1 = num1 + num2;
num2 = num1 - num2;
num1 = num1 - num2;
```



## 3 数据类型

### 查看数据类型

```js
// typeof操作符
console.log(typeof "string");
console.log(typeof(123))
```



### 基本数据类型

#### 数值型 - Number

- 进制表示

```js
var num1 = 10;   // 10
var num2 = 0x10; // 16
var num3 = 0o10; // 8
var num4 = 0b10; // 2
console.log(num1, num2, num3, num4);
```

- 最大数字和最小数字

```js
console.log(Number.MAX_VALUE);
console.log(Number.MIN_VALUE);
```

- NaN(Not a number) 即非数字, 是一个特殊的数值
  - js中当对数值的计算没有结果返回时, 则返回NaN 
- isNaN
  - 用于判断是否是一个数字. 不是数字返回true, 是数字返回false.

```js
console.log(isNaN(123));
```



#### 字符串型 - String

- 转义字符
- 获取字符串的长度 length

```js
var name = 'yanglt';
console.log(name.length);
```



#### 布尔类型 - Boolean

- true / false



#### Undefined 

- 只有一个值 undefined
- 在使用var声明变量但未对其初始化时, 这个变量的值为 undefined
- typeof对没有初始化和没有声明的变量都会返回undefined



#### Null

- 只有一个值 null
- 通常当一个对象(Objective类型)不再使用时, 可以赋值为null

- undefined 和 null 的关系
  - undefined == null  ->  true
  - 转化成数字时, undefined为NaN, null为0



### 数据类型转化

#### 其他类型转化成数字类型

- Number(其他类型)

- parseInt(s: string, radix?: number) 将字符串转成整数类型

- parseFloat(string: string) 将字符串转成浮点数类型

  

```js
    // 1.Number()
    // 1.1 string类型转化成数字类型
    var message1 = "123";
    var num1 = Number(message1);
    console.log(num1, typeof(num1)); // 123 number

    var message2 = 'abc';
    var num2 = Number(message2);
    console.log(num2, typeof(num2)); // NaN number

    // 1.2 将Boolean类型转化成数字类型
    console.log(Number(true));  // 1
    console.log(Number(false)); // 0

    // 1.3 将undefined类型转化成数字类型
    console.log(Number(undefined)); // NaN
    console.log(Number(null));      // 0

    // 2. parseInt()
    var str1 = '123';
    var num1 = parseInt(str1);
    console.log(num1, typeof num1); // 123 number
    
    var str2 = 'abc123';
    var num2 = parseInt(str2);
    console.log(num2, typeof num2); // NaN number

    var str3 = '123abc';
    var num3 = parseInt(str3);
    console.log(num3, typeof num3); // 123 Number
    
    var str4 = '123.45';
    var num4 = parseInt(str4);
    console.log(num4, typeof num4); // 123 Number
	
	var str5 = '111';
    var num5 = parseInt(str5, 2);
    console.log(num5, typeof num5); // 7 Number

    // 3. parseFloat()
    var s1 = '123.45';
    var n1 = parseFloat(s1);
    console.log(n1, typeof n1); // 123.45 number
    
    var s2 = '123.45.67';
    var n2 = parseFloat(s2);
    console.log(n2, typeof n2); // 123.45 number
```



#### 其他类型转化成字符串类型

- 调用toString()方法
- 使用String()函数
- 字符串拼接, 隐式转换



```js
    var num = 123;
    var message = undefined;
    var obj = null;
    var flag = true;  

    // 1. 调用toString()方法
    console.log(num.toString());
    // console.log(message.toString()); undefined不适用
    // console.log(obj.toString()); null不适用
    console.log(flag.toString());

    // 2.使用String()函数
    console.log(String(num));
    console.log(String(message));
    console.log(String(obj));
    console.log(String(flag));

    // 3. 字符串拼接: 变量 + ""
    // 隐式转换: 任何数据类型和字符串通过 + 运算符拼接, 最终结果均转化成字符串类型
    console.log(num + '');
    console.log(message + '');
    console.log(obj + '');
    console.log(flag + '');
```



#### 其他类型转化成布尔类型

- Boolean()



```js
	// 除五个值外的任意数据, 均为true
    console.log(Boolean(123));

    // 五个值: 空字符串"", 0, NaN, null, undefined, 为false
    console.log(Boolean(''));
    console.log(Boolean(0));
    console.log(Boolean(NaN));
    console.log(Boolean(null));
    console.log(Boolean(undefined));
```

