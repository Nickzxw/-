# CSS 

## CSS代码引入方式

行内样式

内部样式表

外部样式表



单位：

**绝对长度单位**

| 单位 | 名称         | 等价换算                 |
| :--- | :----------- | :----------------------- |
| `cm` | 厘米         | 1cm = 37.8px = 25.2/64in |
| `mm` | 毫米         | 1mm = 1/10th of 1cm      |
| `Q`  | 四分之一毫米 | 1Q = 1/40th of 1cm       |
| `in` | 英寸         | 1in = 2.54cm = 96px      |
| `pc` | 派卡         | 1pc = 1/6th of 1in       |
| `pt` | 点           | 1pt = 1/72th of 1in      |
| `px` | 像素         | 1px = 1/96th of 1in      |

**相对长度单位：**

| 单位         | 解释                                                         |
| ------------ | ------------------------------------------------------------ |
| `em`         | 在 `font-size` 中使用是相对于父元素的字体大小，在其他属性中使用是相对于自身的字体大小，如 `width`。 |
| `ex`         | 字符“x”的高度。                                              |
| `ch`         | 数字“0”的宽度。                                              |
| `rem`        | 根元素的字体大小。                                           |
| `lh`         | 元素的行高。                                                 |
| `rlh`        | 根元素的行高。当用于根元素的 `font-size` 或 `line-height` 属性时，它指的是这些属性的初始值。 |
| `vw`         | 视口宽度的 1%。                                              |
| `vh`         | 视口高度的 1%。                                              |
| `vmin`       | 视口较小尺寸的 1%。                                          |
| `vmax`       | 视口大尺寸的 1%。                                            |
| `vb`         | 在根元素的[块向](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Logical_Properties#块向与行向)上，初始包含块的尺寸的 1%。 |
| `vi`         | 在根元素的[行向](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Logical_Properties#块向与行向)上，初始包含块的尺寸的 1%。 |
| `svw`、`svh` | 分别为[视口较小尺寸](https://developer.mozilla.org/zh-CN/docs/Web/CSS/length#基于视口的相对长度单位)的宽度和高度的 1%。 |
| `lvw`、`lvh` | 分别为[视口大尺寸](https://developer.mozilla.org/zh-CN/docs/Web/CSS/length#基于视口的相对长度单位)的宽度和高度的 1%。 |
| `dvw`、`dvh` | 分别为[动态视口](https://developer.mozilla.org/zh-CN/docs/Web/CSS/length#基于视口的相对长度单位)的宽度和高度的 1%。 |

## 基本选择器

*{} - 通用选择器

p{} 标签选择器

.box{} 类选择器

#id{} id选择器

只有块级元素才可以设置宽度和高度，行内元素不可以

块级元素独占一行，行内元素不会强制换行

**因此 div 可以， span 不可以**

## 复合选择器

- 多元素选择器

  - ```css
    p,h1,h2{
        margin: 0px
    }
    ```

- 后代元素选择器

  - ```css
    #slidebar p{
        font-color:#990000
    }
    ```

- 子元素选择器（E>F，匹配所有E元素的子元素F）

  - ```css
    div > p{
        color:#990000
    }
    ```

- 相邻元素选择器（相邻元素选择器，匹配所有紧随E元素之后的同级F元素）

  - ```css
    div + div{
        color:#990000
    }
    ```

## 伪类选择器

### 链接伪类选择器

```
a:link // 选择未访问过的链接
a:visited //选择访问过的链接
a:hover //鼠标经过 ！！！！ 实际开发常用
a:active //鼠标点击
```

### focus 伪类选择器

focus 伪类选择器用于选取获得焦点的表单元素(鼠标光标所在)

```css
input:focus {
    background-color: yellow;
}
```

## 属性选择器

通过标签的属性名和属性值来匹配元素

| 代码          | 解释                               |
| ------------- | ---------------------------------- |
| [attr]        | 匹配选定的属性名的所有元素         |
| [attr=val]    | 匹配属性等于指定值的所有元素       |
| [attr*="val"] | 匹配属性中包含指定值的所有元素     |
| [attr$="val"] | 匹配属性的值以指定值结束的所有元素 |
| [attr^="val"] | 匹配属性以指定值开头的所有元素     |

## 元素显示模式

块元素的特点

- 独占一行
- 高度、宽度、外边距和内边距都可以控制
- 宽度默认是容器的100%
- 是一个容器以及盒子，里面可以放行内或者块级元素

行内元素的特点：

- 相邻元素在同一行
- 高、宽直接设置无效
- 默认宽度是内容的宽度
- 行内元素只能容纳文本或其他行内元素（不能包含块级元素）

行内块元素（同时拥有块级元素和行内元素的特点）：

- 和相邻行内元素/行内块元素在一行上。一行可以显示多个（行内元素特点）
- 默认宽度是它本身内容的宽度（行内元素）
- 高度、行高、外边距和内边距都可以控制（块级元素）

### 元素显示模式转换

转块级

```css
display: block；
```

转行内

```css
display: inline;
```

转行内块

```css
display: inline-block;
```

## 背景

| 背景         | 代码                                                         |
| ------------ | ------------------------------------------------------------ |
| 背景颜色     | background-color                                             |
| 背景图片     | background-iimage                                            |
| 背景平铺     | background-repeat : repeat / repeat-x / repeat-y / no-repeat |
| 背景位置     | background-position: x y;（长度/方位词-默认值是居中）        |
| 背景图像固定 | background-attachment 是否随着页面部分滚动                   |

复合属性：background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

背景颜色半透明： rgba()alpha 透明度

## CSS三大特性

#### 层叠性

样式冲突问题，就近元素，哪一个样式离元素近，就执行谁（样式覆盖）

#### 继承性

子标签会继承父标签的某些样式（主要是文字相关样式text- font- line- 、以及颜色color）

#### 优先级

| 选择器               | 选择器权重 |
| -------------------- | ---------- |
| 继承 或 *            | 0000       |
| 元素选择器           | 0001       |
| 类选择器，伪类选择器 | 0010       |
| ID选择器             | 0100       |
| 行内样式             | 1000       |
| !important           | 无穷大     |

注意事项：继承的权重是0

**复合选择器会有权重叠加的问题，选择器权重累加，有叠加但不会进位！！！**

## 盒子模型

content、border、padding、margin

| 属性         | 作用                                          |
| ------------ | --------------------------------------------- |
| border-width | 定义边框粗细，单位是px                        |
| border-style | 边框的样式 solid 实线 dashed 虚线 dotted 点线 |
| border-color | 边框颜色                                      |

边框简写：1px solid red

**边框会影响盒子的实际大小**

| 属性                        | 作用                                 |
| --------------------------- | ------------------------------------ |
| padding: 5px;               | 1个值，代表上下左右都是5px           |
| padding: 5px 10px;          | 2个值，上下是5px，左右是10px         |
| padding: 5px 10px 20px;     | 3个值，上5px，左右10px，下位20px     |
| padding: 5px 10px 20px 30px | 4个值，上5px，右10px，下20px，左30px |

**padding 也会影响盒子的实际大小**

## 网页布局的三种方式

### 标准流

### 浮动流

为什么需要浮动，浮动可以改变元素默认的排列方式，可以让多个块级元素一行内排列显示。

什么是浮动：float 用于创建浮动框，将其移动到一边，直到触碰到左边缘、右边缘或另一个浮动框的边缘。

**网页布局第一准则：多个块级元素，纵向排列找标准流，横向排列找浮动流**

浮动的特性：

- 浮动元素脱离标准流（脱标）
- 浮动的盒子不再保留原先的位置
- 浮动元素具有行内块元素的特性（任何元素均可浮动）

浮动盒子只会影响后面的标准流

清除浮动：父级盒子不方便给高度，但子盒子浮动不占有位置，最后父级盒子高度为0时，就会影响下面的标准流盒子

clear: left/right/both

清除浮动的方法：

- 额外标签法！！
- 父级添加 overflow 属性
- 父级添加after为元素
- 父级添加双伪元素
- (要不还是给个高度吧哈哈)

```css
/*清除浮动*/
    .clearfix:before, .clearfix:after {
      content: "";
      display: table;
    }
    .clearfix:after {
      clear: both;
    }
    .clearfix {
      *zoom: 1;
    }
```



### 定位流

为什么定位？

定位可以让盒子自由的在某个盒子内移动位置或者固定屏幕中某个位置，可以压住其他盒子

定位 = 定位模式+边偏移

定位模式用于指定一个元素在文档中的定位模式

边偏移决定元素的最终位置

position : 

- static 静态定位 标准流
- relative  相对定位，相对于自己原来的位置，移动后在标准流的位置保留（不脱标）（常用来给绝对定位当爹）
- absolute 绝对定位相对于父元素，没有父元素或者父元素没有定位就以浏览器为准定位（拖标）
- 子绝父相（子元素 绝对定位则 父元素相对定位）
- fixed 以浏览器的可视窗口为参照点移动元素， 不随滚动条滚动（拖标）
  - 如何固定在版心右侧：算法（可视区域的一般+ 版心的一半（可以用margin））
- sticky 粘性定位，相对定位和固定定位的混合
  - 根据可视窗口为参照点移动元素（固定定位特点）
  - 粘性定位占有原先的位置（相对定位特点）
  - 需要设置 top、right、bottom、left 至少一个

边偏移： top right bottom left

绝对定位盒子居中：可视区域的50% + margin 取盒子宽度50%的负值

叠放顺序：z-index  层级相同HTML后面的元素后来者居上

定位的特殊特性：行内元素加了定位就可以加高度和宽度，块级元素加定位宽度高度变成内容的大小

## CSS 属性书写顺序

1. 布局定位属性：display position float celar visbility overflow
2. 自身属性 width height margin padding border background
3. 文本属性 color font text-decoration text-align 
4. 其他属性

## 元素的显示与隐藏

display : none（隐藏对象） block （显示元素） 隐藏会脱标

visibility :  visible hidden 不脱标

overflow :  visible auto hidden 

## CSS 高级技巧

### CSS 雪碧图

通过 background-position：x, y 来定位图片

## HTML 5 新特性

新增语义化标签

- header 头部标签
- nav 导航标签
- article 内容标签
- section 定义文档某个区域
- aside 侧边栏标签
- footer  尾部标签

新增多媒体标签：

- 音频：<audio> MP3
- 视频：<video> MP4

新增input类型：

- type = "email"
- type = "url" 输入类型必须为 url
- type = "date"
- type = "time"
- type = "month"
- type = "week"
- type = "number"
- type = "tel" 输入类型为手机号码
- type = "search" 输入类型搜索框
- type = "color" 颜色选择表单

新增的表单属性：

- required 表单拥有该属性表示其内容不能为空
- placeholder 提示文本
- multiple 可以多选文件提交

## CSS 3新特性

结构伪类选择器：

- e: first-child
- e: last-child
- e: nth-child(n) 匹配父元素中的第n个子元素E
  - n 除了数字还可以是关键字，even 偶数， odd 奇数 或者公式 2n / 2n+1
- e：first-of-type 指定类型E的第一个
- e：last-of-type 指定类型E的最后一个

伪元素选择器：

- ::after
- ::before

盒子模型：

box-sizing: border-box width多大 盒子就多大 不会被撑开

过渡（transition）：

- trainsition : 属性 花费时间 运动曲线 何时开始；
- 谁做过渡给谁加
