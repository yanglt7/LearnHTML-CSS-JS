# 内容概述

## 一、HTML-表单元素

### 1.1 input的属性(type, maxlength, placeholder)

* type
  * text
    * 明文形式
  * password
    * 密文形式
  * file
    * 文件上传
  * button
    * 按钮
  * radio
    * 单选框
    * name 需要相同
  * checkbox
    * 多选框
* select
  * 下拉选择
  * size 
    * 显示多少项
  * multiple
    * 可以多选
* option
  * selected
    * 默认被选中
* maxlength
  * 允许输入的最大长度
* name
  * 上传数据到服务器的key
* value
  * 上传数据到服务器的value
* placeholder
  * 默认显示的文字

![image-20200112134056068](day07_html表单元素.assets/image-20200112134056068.png)

* textarea

  * cols
    * 列数
  * rows
    * 行数
  * resize
    * none 禁止缩放
    * horizontal 水平缩放
    * vertical 垂直缩放
    * both(默认值) 水平垂直缩放

  

### 1.2 input的布尔属性(checked, selected)

* readonly
  * 只读(不常用)
* disabled
  * 禁用
* checked
  * 默认选中
  * 只能用于radio单选框和checkbox多选框
* autofocus
  * 页面打开后默认聚焦
  * 常用于第一个输入框
* selected
  * 默认选中
  * 用于option下拉选择
* multiple
  * 多选(少用)

### 1.3 fieldset - legend

![image-20200112134147377](day07_html表单元素.assets/image-20200112134147377.png)



![image-20200112134513746](day07_html表单元素.assets/image-20200112134513746.png)



### 1.4 按钮的实现方式

![image-20200112141659072](day07_html表单元素.assets/image-20200112141659072.png)



### 1.5 input和label的关系

![image-20200112142728734](day07_html表单元素.assets/image-20200112142728734.png)

![01-input&label](day07_html表单元素.assets/01-input&label-1578824888858.gif)



### 1.6 CSS reset(outline:none)

![image-20200112143908046](day07_html表单元素.assets/image-20200112143908046.png)



### 1.7 表单提交

* 传统的表单提交
  * 将所有的input包裹到一个form中
  * form设置action(服务器地址)
  * input/button类型是submit
  * 点击submit, 自动将所有的数据提交到服务器
  * 弊端1
    * 会进行页面的跳转(意味着服务器必须有写好的一个页面, 返回给前端, 前端直接展示这个页面)
    * 服务器提交将页面写好: 服务端渲染(利于SEO优化)
  * 弊端2
    * 不方便进行表单数据的验证
* 前后端分离
  * 通过JavaScript获取到所有表单内容
  * 通过正则表达式进行表单的验证
  * 发送ajax请求, 将数据发送给服务器
  * 服务器会返回结果, 需要前端解析这个数据, 并且决定显示什么内容(前端渲染和前端路由)



### 1.8 form的常用属性

* action
  * 用于提交表单数据的请求url
* method
  * 请求方法(GET和POST), 默认是GET
* target
  * 在什么地方打开URL(参考a元素的target)
* accept-charset
  * 默认是 unknown
* enctype
  * input type有一个file类型时, 需要设置成 multipart/form-data
