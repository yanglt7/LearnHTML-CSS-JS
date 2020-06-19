# 内容概述

## 1 html5 补充

### 1.1 语义化元素

- \<header>：头部元素
- \<nav>：导航元素
- \<section>：定义文档某个区域的元素
- \<article>：内容元素
- \<aside>：侧边栏元素
- \<footer>：尾部元素



### 1.2 媒体元素

#### 1.2.1 视频 - video

- src：媒体的来源
- controls：增加控制工具栏
- autoplay：自动播放，存在浏览器兼容问题
- muted：静音，增加后不静音并且自动播放生效
- loop：循环播放
- \<source>元素
  - 如果存在兼容性问题，可以将多个视频格式的数据源放到source元素中
  - src：通过src指定数据的来源

#### 1.2.2 音频 - audio

- src：媒体的来源
- controls：增加控制工具栏
- autoplay：自动播放，存在浏览器兼容问题
- muted：静音，增加后不静音并且自动播放生效
- loop：循环播放
- \<source>元素
  - 如果存在兼容性问题，可以将多个音频格式的数据源放到source元素中
  - src：通过src指定数据的来源

### 1.3 表单元素的扩展

- placeholder：输入框占位文字

- multiple：选择多个值

- autofocus：自动对焦

- type

  - 原有属性：text/password/button/checkbox/radio/submit/reset
  - h5扩展属性：date/time/number/tel/color/email

  

## 2 transform 形变

- css transform 属性允许旋转/缩放/倾斜/平移给定元素
  - transform对行内元素不生效
- 常见的函数: transform function 有:
  - 平移 translate(x, y)
  - 缩放 scale(x, y)
  - 旋转 rotate(deg)
  - 倾斜 skew(deg, deg)



### 2.1 平移 translate(x, y)



- 值个数
  - 一个值时, 设置x轴上的位移
  - 两个值时, 设置x轴和y轴上的位移
- 值类型
  - 数字: 100px
  - 百分比: 参照元素本身



### 2.2 缩放 scale(x, y)

- 值个数
  - 一个值时, 设置x轴和y轴相同的缩放
  - 两个值时, 设置x轴和y轴的缩放
- 值类型
  - 数字
    - 2: 放大一倍
    - 1: 保持不变
    - 0.5: 缩小一半
  - 百分比: 不支持百分比



### 2.3 变形的原点 transform-origin

- 一个值

  - 设置x轴的原点

- 两个值

  - 设置x轴和y轴的原点

- 必须是\<length>,  \<percentage>, 或 left, center, right, top, bottom 关键字中的一个

  - left, center, right, top, bottom 关键字

  - length: 从左上角开始计算

  - 百分比: 参考元素本身大小

    

### 2.4 旋转 rotate(deg)

- 值个数
  - 一个值时, 表示旋转的角度
- 值类型
  - deg: 旋转的角度
  - 正数为顺时针
  - 负数为逆时针
- 注意: 旋转的原点受transform-origin的影响



### 2.5 倾斜 skew(deg, deg)

- 值个数
  - 一个值时, 表示x轴上的倾斜
  - 两个值时, 表示x轴和y轴上的倾斜
- 值类型
  - deg: 旋转的角度
  - 正数为顺时针
  - 负数 为逆时针
- 注意: 旋转的原点受transform-origin的影响



## 3 transition 过渡动画

- transition CSS 属性是 transition-property, transition-duration, transition-timing-function, transition-delay 的一个简写属性
- transition-property: 指应用过渡属性的名称
  - 可以写 all 代表所有可动画的属性
  - 属性是否支持动画查看文档
- transition-duration: 指过渡动画所需时间
  - 单位可以是秒(s)或毫秒(ms)
- transition-timing-funciton: 指定动画的变化曲线
- transition-delay: 指定过渡动画执行之前的等待时间





## 4 vertical-align

- 取值
  - baseline(默认值): 基线对齐
    - 文本的baseline是字母x的下方
    - inline-block默认的baseline是margin-bottom的底部(若无, 则是盒子的底部)
    - inline-block有文本时,  baseline就是最后一行文本的x的下方
  - top:  行内级盒子的顶部和line boxes顶部对齐
  - middle:  行内级盒子的中心点和父盒基线加上x-height一半的线对齐
  - bottom:  行内级盒子的底部和line boxes底部对齐
  - \<percentage>:  行内级盒子提升或下降一段距离(距离相对line-height计算\\元素高度), 0%意味着同baseline一样
  - \<length>:  行内级盒子提升或下降一段距离, 0cm意味着同baseline一样



## 5 隐藏元素的方式

- display: none
- visibility: hidden
- opacity: 0 (不透明度)



## 6 网络字体和字体图标

- @font-face可以让网页支持网络字体(web font), 不再局限于系统自带的字体
- 常见的字体种类:
  - TrueType字体: 扩展名是 .ttf
  - OpenType字体: 扩展名是 .ttf , .otf , 建立在 TrueType 字体之上
  - Embedded OpenType字体: 扩展名是 .eot , OpenType 字体的压缩版
  - SVG字体: 扩展名是 .svg , .svgz
  - web开放字体: 扩展名是 .woff, 建立在 TrueType 字体之上
- 并不是所有浏览器都支持以上字体, 使用时需要多加测试

### 使用图片的方式

- img元素
  - 网站的重要组成部分
  - 不能使用精灵图
- background-image
  - 装饰作用
  - 先加载css -> URL
  - 可以使用精灵图 -> background-position
- iconfont字体图标
  - 字体图标放大不会失真
  - 图片过多时, 减少请求次数, 相当于压缩图片



## 7 动画补充

### @keyframes 关键帧动画

- transition 可进行过渡动画,但是过渡动画只能控制首尾两个值
  - 从关键帧的角度相当于只是定义了两帧的状态: 第一帧和最后一帧
  - 如果希望有更多状态的变化, 可以使用关键帧动画
  - 关键帧动画使用 @keyframes 来定义多个变化状态, 并且使用 animation-name 来声明匹配
    - 使用 @keyframes 创建一个规则
    - @keyframes 中使用百分比来定义各个阶段的样式
    - 通过 animation 将动画添加到属性上
  - 另外, 也可以使用 from 和 to 两个关键字
    - from = 0%
    - to = 100%

### 3D动画

- CSS实现3D
  - transform-style: preserve-3d
  - perspective
- js实现3D的库
  - three.js



## 8 浏览器前缀

- 有些CSS属性名前面带有: 	-o- / -xv- / -mso- / -moz- / -wbkit-
- 上述前缀叫浏览器私有前缀, 只有对应的浏览器才能解析使用
- 官方文档的术语叫 : vendor-specific extensions (供应商特定扩展)
- 不需要手动添加, 模块化打包工具会自动添加浏览器前缀



## 9 文字处理

- white-space用于设置空白处理和换行规则
  - normal：合并所有连续空白，允许单词超屏时自动换行
  - nowrap：合并所有连续空白，不允许单词超屏时自动换行
- text-overflow通常用来设置文字溢出时的行为(处理那部分不可见的内容)
  - clip：溢出的内容直接剪裁掉(字符可能显示不完整)
  - ellipsis：溢出那行的结尾处用省略号表示
  - text-overflow生效的前提是overflow不为visible



##  10 移动端适配

- 设置内容大小的方式
  - px 设置为固定的css像素
  - em 相对于父元素的字体大小
  - rem 相对于根元素(html)的字体大小

- 移动端开发中rem适配方法
  - 针对不同的手机屏幕大小，设置不同html的font-size大小
  - 将所有需要适配的图片/字体/宽高度等, 单位改成rem
- 问题一：动态设置html的font-size
  - 法一: 媒体查询
  - 法二: js动态计算(最优方案)
- 问题二：动态计算rem值
  - 法一：利用vscode的插件快速转化
    - 插件 px to rem
  - 法二：利用postcss-pxtorem(最优方案)
  - 法三：利用less、sass、stylus的计算能力