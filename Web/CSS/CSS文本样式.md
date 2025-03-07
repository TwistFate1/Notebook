# 为文本添加样式（样式化文本）

## 基本文本和字体样式

### CSS 中的文字样式涉及什么？

- 字体样式: 作用于字体的属性，会直接应用到文本中，比如使用哪种字体，字体的大小是怎样的，字体是粗体还是斜体，等等。

- 文本布局风格: 作用于文本的间距以及其他布局功能的属性，比如，允许操纵行与字之间的空间，以及在内容框中，文本如何对齐。

### 字体

#### 颜色

#### 字体种类

> 网页安全字体：

| 字体名称 | 泛型 | 注意 |
| :-: | :-: | :-: |
| Arial | sans-serif | 通常认为最佳做法还是添加 Helvetica 作为 Arial 的首选替代品，尽管它们的字体面几乎相同，但 Helvetica 被认为具有更好的形状，即使 Arial 更广泛地可用。 |
| Courier New | monospace | 某些操作系统有一个 Courier New 字体的替代（可能较旧的）版本叫 Courier。使用 Courier New 作为 Courier 的首选替代方案，被认为是最佳做法。 |
| Georgia | serif |  |
| Times New Roman | serif | 某些操作系统有一个 Times New Roman 字体的替代（可能较旧的）版本叫 Times。使用 Times 作为 Times New Roman 的首选替代方案，被认为是最佳做法。 |
| Trebuchet MS | sans-serif | 你应该小心使用这种字体——它在移动操作系统上并不广泛。 |
| Verdana | sans-serif |  |

> 默认字体：

| 名称 | 定义 |
| :-: | :-: |
| `serif` | 衬线字体，即有衬线的字体（衬线是指字体笔画尾端的小装饰，存在于某些印刷体字体中）。 |
| `sans-serif` | 无衬线字体。 |
| `monospace` | 等宽字体，指包含的全部字符的宽度相同的字体，通常在编辑代码时使用。 |
| `cursive` | 手写字体，对于英文字符而言通常具有顺滑的连接笔画以模拟手写效果。 |
| `fantasy` | 装饰字体。 |

> 字体栈。只需包含一个 `font-family` 属性，其值由几个用逗号分离的字体名称组成。比如：

```css
p {
  font-family: "Trebuchet MS", Verdana, sans-serif;
}
```

**备注：** 有一些字体名称不止一个单词，比如Trebuchet MS ，那么就需要用引号包裹。

#### 字体大小

> 字体大小（通过 `font-size` 属性设置）可以取大多数这些单位的值 (以及其他，比如百分比)。

#### 字体样式、字体粗细、文本转换和文本装饰

> CSS 提供了 4 种常用的属性来改变文本的样子：

- `font-style`: 用来打开和关闭文本 italic (斜体)。可能的值如下 (你很少会用到这个属性，除非你因为一些理由想将斜体文字关闭斜体状态)：

  - `normal`: 将文本设置为普通字体 (将存在的斜体关闭)

  - `italic`: 如果当前字体的斜体版本可用，那么文本设置为斜体版本；如果不可用，那么会利用 oblique 状态来模拟 italics。
  - `oblique`: 将文本设置为斜体字体的模拟版本，也就是将普通文本倾斜的样式应用到文本中。

- `font-weight`: 设置文字的粗体大小。这里有很多值可选 (比如 -light, -normal, -bold, -extrabold, -black, 等等), 不过事实上你很少会用到 `normal` 和 `bold` 以外的值：

  - `normal`, `bold`: 普通或者加粗的字体粗细
  
  - `lighter`, `bolder`: 将当前元素的粗体设置为比其父元素粗体更细或更粗一步。`100`–`900`: 数值粗体值，如果需要，可提供比上述关键字更精细的粒度控制。

- `text-transform`: 允许你设置要转换的字体。值包括：

  - `none`: 防止任何转型。

  - `uppercase`: 将所有文本转为大写。

  - `lowercase`: 将所有文本转为小写。

  - `capitalize`: 转换所有单词让其首字母大写。

  - `full-width`: 将所有字形转换成全角，即固定宽度的正方形，类似于等宽字体，允许拉丁字符和亚洲语言字形（如中文，日文，韩文）对齐。
  
- `text-decoration`: 设置/取消字体上的文本装饰 (你将主要使用此方法在设置链接时取消设置链接上的默认下划线。) 可用值为：

  - `none`: 取消已经存在的任何文本装饰。

  - `underline`: 文本下划线。

  - `overline`: 文本上划线

  - `line-through`: 穿过文本的线。

#### 文字阴影

> 你可以为你的文本应用阴影，使用 `text-shadow` 属性。

#### 多种阴影

> 你可以通过包含以逗号分隔的多个阴影值，将多个阴影应用于同一文本。

### 文本布局

#### 文本对齐

> `text-align` 属性用来控制文本如何和它所在的内容盒子对齐。

#### 行高

> `line-height` 属性设置文本每行之间的高，可以接受大多数单位 length and size units，不过也可以设置一个无单位的值，作为乘数，通常这种是比较好的做法。无单位的值乘以 `font-size` 来获得 `line-height`。

#### 字母和单词间距

> `letter-spacing` 和 `word-spacing` 属性允许你设置你的文本中的字母与字母之间的间距、或是单词与单词之间的间距。你不会经常使用它们，但是可能可以通过它们，来获得一个特定的外观，或者让较为密集的文字更加可读。

#### 其他一些值得看一下的属性

> Font 样式：

- `font-variant`: 在小型大写字母和普通文本选项之间切换。

- `font-kerning`: 开启或关闭字体间距选项。

- `font-feature-settings`: 开启或关闭不同的 OpenType 字体特性。

- `font-variant-alternates`: 控制给定的自定义字体的替代字形的使用。

- `font-variant-caps`: 控制大写字母替代字形的使用。

- `font-variant-east-asian`: 控制东亚文字替代字形的使用，像日语和汉语。

- `font-variant-ligatures`: 控制文本中使用的连写和上下文形式。

- `font-variant-numeric`: 控制数字，分式和序标的替代字形的使用。

- `font-variant-position`: 控制位于上标或下标处，字号更小的替代字形的使用。

- `font-size-adjust`: 独立于字体的实际大小尺寸，调整其可视大小尺寸。

- `font-stretch`: 在给定字体的可选拉伸版本中切换。

- `text-underline-position`: 指定下划线的排版位置，通过使用 `text-decoration-line` 属性的 `underline` 值。

- `text-rendering`: 尝试执行一些文本渲染优化。

> 文本布局样式：

- `text-indent`: 指定文本内容的第一行前面应该留出多少的水平空间。

- `text-overflow`: 定义如何向用户表示存在被隐藏的溢出内容。

- `white-space`: 定义如何处理元素内部的空白和换行。

- `word-break`: 指定是否能在单词内部换行。

- `direction`: 定义文本的方向 (这取决于语言，并且通常最好让 HTML 来处理这部分，因为它是和文本内容相关联的。)

- `hyphens`: 为支持的语言开启或关闭连字符。

- `line-break`: 对东亚语言采用更强或更弱的换行规则。

- `text-align-last`: 定义一个块或行的最后一行，恰好位于一个强制换行前时，如何对齐。

- `text-orientation`: 定义行内文本的方向。

- `word-wrap`: 指定浏览器是否可以在单词内换行以避免超出范围。

- `writing-mode`: 定义文本行布局为水平还是垂直，以及后继文本流的方向。

## 为列表添加样式

### 列表特定样式

#### 符号样式

> `list-style-type`：设置用于列表的项目符号的类型，例如无序列表的方形或圆形项目符号，或有序列表的数字、字母或罗马数字。

#### 项目符号位置

> `list-style-position`：设置在每个项目开始之前，项目符号是出现在列表项内，还是出现在其外。

#### 使用自定义的项目符号图片

> `list-style-image`：允许为项目符号使用自定义图片，而不是简单的方形或圆形。

### 管理列表计数

#### start

> `start` 属性允许你从 1 以外的数字开始计数。

#### reversed

> `reversed` 属性将使列表反向计数。

#### value

> `value` 属性允许设置列表项指定数值。

## Web 字体

> Web 字体是一种 CSS 特性，允许你指定在访问时随你的网站一起下载的字体文件，这意味着任何支持 Web 字体的浏览器都可以使用你指定的字体。

```css
@font-face {
  font-family: "myFont";
  src: url("myFont.ttf");
}
```
