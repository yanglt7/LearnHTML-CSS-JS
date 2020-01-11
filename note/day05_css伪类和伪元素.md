# 内容概述

## 一、伪类

* 目标伪类 target 
* 元素状态伪类 disabled/enable/checked(input)
* 动态伪类
  * link: a
  * visited: a
  * focus: a和input
  * hover 其他元素
  * active 其他元素
* 结构伪类
  * nth-child
    * 数字
    * n -> 2n+1 -> -n+3
    * odd/even
  * nth-last-child
    * 从后往前数
  * nth-of-type
    * 相同类型
    * 忽略不同类型
  * first-child
  * last-child
  * first-of-type
  * last-of-type
  * only-child
  * empty
  * root
* 否定伪类
  * 特殊场景下使用
  * class不香吗?



## 二、伪元素

* first-line
* first-letter
* before
* after
* 建议: 使用两个冒号



## 三、Emmet语法

* !
  * 生成HTML模板
* \> 
  * 直接后代元素
* +
  * 兄弟元素
* *
  * 乘以数字
* ^
  * 跳到上一级
* ()
  * 分组
* 属性#id/.class/普通
  * 默认div可以省略(隐式标签)
* {}
  * 内容
* $ 
  * 数字
* 隐式标签
  * div
  * ul>.item
  * table>.row
* css 属性

