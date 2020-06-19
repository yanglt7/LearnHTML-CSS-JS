# 内容概述

## 1 数组的基本操作

```js
    var names = ['Kobe', 'James', 'Andy', 'Jasper'];

    // 1.数组的长度属性: length
    var len = names.length;
    console.log(len);

    // 2.根据索引值获取数据
    // 如果输入不存在的索引值, 返回的数据是 undefined
    // 不支持负数索引, 返回的数据是 undefined
    var name = names[0];
    console.log(name);
```



## 2 数组的遍历

```js
    var names = ['Kobe', 'James', 'Andy', 'Jasper'];

    for (var i = 0; i < names.length; i++) {
      console.log(names[i]);
    }

    // ES6
    for (let i in names) {
      console.log(names[i]);
    }

    for (let name of names) {
      console.log(name);
    }
```

