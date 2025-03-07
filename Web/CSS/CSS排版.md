# CSS 排版

## 介绍 CSS 布局

### 正常布局流

> 正常布局流（normal flow）是指在不对页面进行任何布局控制时，浏览器默认的 HTML 布局方式。

### display 属性

> 在 css 中实现页面布局的主要方法是设定display属性的值。此属性允许我们更改默认的显示方式。

### 弹性盒子

> Flexbox 是 CSS 弹性盒子布局模块（Flexible Box Layout Module）的缩写，它被专门设计出来用于创建横向或是纵向的一维页面布局。

#### Grid 布局

> Flexbox 用于设计横向或纵向的布局，而 Grid 布局则被设计用于同时在两个维度上把元素按行和列排列整齐。

#### 浮动

> 把一个元素“浮动”(float) 起来，会改变该元素本身和在正常布局流（normal flow）中跟随它的其他元素的行为。这一元素会浮动到左侧或右侧，并且从正常布局流 (normal flow) 中移除，这时候其他的周围内容就会在这个被设置浮动 (`float`) 的元素周围环绕。

### 定位技术

#### 相对定位

> 相对定位 (relative positioning) 让你能够把一个正常布局流 (normal flow) 中的元素从它的默认位置按坐标进行相对移动。

#### 绝对定位

> 绝对定位用于将元素移出正常布局流 (normal flow)，以坐标的形式相对于它的容器定位到 web 页面的任何位置，以创建复杂的布局。

#### 固定定位

> 固定定位 (fixed positioning) 同绝对定位 (absolute positioning) 一样，将元素从文档流 (document flow) 当中移出了。但是，定位的坐标不会应用于"容器"边框来计算元素的位置，而是会应用于视口 (viewport) 边框。

#### 粘性定位

> 粘性定位 (sticky positioning) 是最后一种我们能够使用的定位方式。它将默认的静态定位 (static positioning) 和固定定位 (fixed positioning) 相混合。当一个元素被指定了position: sticky时，它会在正常布局流中滚动，直到它出现在了我们给它设定的相对于容器的位置，这时候它就会停止随滚动移动，就像它被应用了 `position: fixed` 一样。

### 表格布局

### 多列布局

> 要把一个块转变成多列容器 (multicol container)，我们可以使用 `column-count` 属性来告诉浏览器我们需要多少列，也可以使用 `column-width` 来告诉浏览器以至少某个宽度的尽可能多的列来填充容器。

## 浮动内容

### 清除浮动

> 如果我们不想让剩余元素也受到浮动元素的影响，我们需要停止它；这是通过添加 `clear` 属性实现的。
>
> `clear` 属性接受下列值：

- `left`：停止任何活动的左浮动

- `right`：停止任何活动的右浮动

- `both`：停止任何活动的左右浮动

## 媒体查询

### 媒体查询基础

```css
@media media-type and (media-feature-rule) {
  /* CSS rules go here */
}
```

- 一个媒体类型，告诉浏览器这段代码是用在什么类型的媒体上的（例如印刷品或者屏幕）；

- 一个媒体表达式，是一个被包含的 CSS 生效所需的规则或者测试；

- 一组 CSS 规则，会在测试通过且媒体类型正确的时候应用。

#### 媒体类型

- all

- print

- screen

- speech

#### 媒体特征规则

- 宽和高

    > 可以使用 `min-width`、`max-width` 和 `width` 媒体特征，在视口宽度大于或者小于某个大小——或者是恰好处于某个大小——的时候，应用 CSS。

- 朝向

    > `orientation`，我们可以用它测得竖放（portrait mode）和横放（landscape mode）模式。

- 使用指点设备

### 更复杂的媒体查询

#### 媒体查询中的“与”逻辑

```css
@media screen and (min-width: 400px) and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

#### 媒体查询中的“或”逻辑

```css
@media screen and (min-width: 400px), screen and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

#### 媒体查询中的“非”逻辑

```css
@media not all and (orientation: landscape) {
  body {
    color: blue;
  }
}
```

### 怎么选择断点

> 引入媒体查询的点就叫做断点。
