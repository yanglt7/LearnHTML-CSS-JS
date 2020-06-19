# 内容概述

## 1 分支语句

### 单分支、多分支语句

```js
    var age = prompt("请输入你的年龄:");

    if (age >= 18) {
      console.log('成年');
    }

    if (age < 18) {
      console.log('未成年');
    } else {
      console.log('成年');
    }

    if (age < 18) {
      console.log('未成年');
    } else if (age < 60) {
      console.log('成年');
    } else {
      console.log('老年');
    }
```



### 三目运算符

```js
    var m = 10, n = 8;
    var max = m > n ? m : n;
    console.log(max);

    var age = prompt();
    var result = age >= 18 ? "成年人" : "未成年人";
    console.log(result);
```



### switch语句

```js
	var holidayName = prompt("请输入今天的节日:");
    switch (holidayName) {
        case "情人节":
          console.log("买玫瑰");
          console.log("看电影");
          break;
        case "平安夜":
          console.log("买苹果");
          console.log("吃大餐");
          break;
        case "生日":
          console.log("买蛋糕");
          console.log("送礼物");
          break;
        default:
          console.log("上班");
          console.log("喝西北风");
          break;
    }
```





## 2 循环语句

```js
    // while循环
    var i = 0;
    while (i < 10) {
      console.log(i, "Hello World!");
      i++;
    }

    // do while循环
    var n = 0;
    do {
      console.log(n, "Hello World!");
      n++;
    } while (n < 10);

    // for循环
    for (var j = 0; j < 10; j++) {
      console.log(j, "Hello World!");
    }

    for (var p = 0; p < 9; p++) {
      for (var q = 0; q <= p; q++) {
        document.write("❤ ");
      }
      document.write('<br>');
    }

    document.write('<div>');
    for (var a = 1; a < 10; a++) {
      for (var b = 1; b <= a; b++) {
        var str = '<span>' + b + '*' + a + '=' + a*b + '</span>';
        document.write(str);
        if (a === b) {
          document.write('<br>');
        }
      }
    }
    document.write('</div>');
```



```css
    div {
      display: inline-block;
      border-left: 1px solid #ff1e32;
      border-bottom: 1px solid #ff1e32;
    }

    span {
      display: inline-block;
      text-align: center;
      width: 80px;
      height: 30px;
      line-height: 30px;
      border-top: 1px solid #ff1e32;
      border-right: 1px solid #ff1e32;
    }
```



### continue / break

- continue
  - 跳过本次循环
- break
  - 跳出循环



```js
    // 当i=5或i=8时, 不打印
    for (var i = 0; i < 10; i++) {
      if (i === 5 || i === 8) {
        continue;
      }
      console.log(i, 'Hello World!');
    }

    // 当i=5时, 停止打印
    for (var j = 0; j < 10; j++) {
      if (j === 5) {
        break;
      }
      console.log(j, 'Hello World!');
    }
```

