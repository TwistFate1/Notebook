# HTML 指南

## 内容分类

- 主内容类，描述了很多元素共享的规则；

- 表单相关的内容类，描述了表单相关元素共有的规则；

- 特殊内容类，描述了仅仅在少数元素（有时仅在特定的上下文中）共享的规则。

### 主内容类

#### 元数据内容

> 属于元数据内容（Metadata content）的元素可以修改文档其余部分的呈现或行为、建立与其他文档的链接，或者传达其他带外信息。
>
> 属于这一类的元素有：`<base>`、`<link>`、`<meta>`、`<noscript>`、`<script>`、`<style>` 和 `<title>`。

#### 流式内容

> 流式内容（Flow content）是一个广泛的类别，包括大多数可以包含在 `<body>` 元素之内的元素，包括标题元素、分段元素、短语元素、嵌入元素、交互元素和表单相关元素。它还包括文本节点（但不包括那些只由空白字符组成的节点）。
>
> 流式元素有：

- `<a>`

- `<abbr>`

- `<address>`

- `<article>`

- `<aside>`

- `<audio>`

- `<b>`

- `<bdo>`

- `<bdi>`

- `<blockquote>`

- `<br>`

- `<button>`

- `<canvas>`

- `<cite>`

- `<code>`

- `<data>`

- `<datalist>`

- `<del>`

- `<details>`

- `<dfn>`

- `<dialog>`

- `<div>`

- `<dl>`

- `<em>`

- `<embed>`

- `<fieldset>`

- `<figure>`

- `<footer>`

- `<form>`

- `<h1>-<h6>`

- `<header>`

- `<hgroup>`

- `<hr>`

- `<i>`

- `<iframe>`

- `<img>`

- `<input>`

- `<ins>`

- `<kbd>`

- `<label>`

- `<main>`

- `<map>`

- `<mark>`

- `<math>`

- `<menu>`

- `<meter>`

- `<nav>`

- `<noscript>`

- `<object>`

- `<ol>`

- `<output>`

- `<p>`

- `<picture>`

- `<pre>`

- `<progress>`

- `<q>`

- `<ruby>`

- `<s>`

- `<samp>`

- `<search>`

- `<script>`

- `<section>`

- `<select>`

- `<slot>`

- `<small>`

- `<span>`

- `<strong>`

- `<sub>`

- `<sup>`

- `<svg>`

- `<table>`

- `<template>`

- `<textarea>`

- `<time>`

- `<u>`

- `<ul>`

- `<var>`

- `<video>`

- `<wbr>`

- 纯文本

- `<area>`，当它为 `<map>` 元素的子元素时

- `<link>`，若存在 `itemprop` 属性

- `<meta>`，若存在 `itemprop` 属性

#### 分段内容

> 分段内容（Sectioning content）是流式内容的一个子集，可以在当前大纲中创建一个分段，它定义了 `<header>` 元素、`<footer>` 元素和标题内容的范围。
>
> 属于此类的元素有：`<article>`、`<aside>`、`<nav>` 和 `<section>`。

#### 标题内容

> 标题内容（Heading content）是流式内容的一个子集，定义了分段的标题，而这个分段可能由一个明确的分段内容元素直接标记，也可能由标题本身隐式地定义。
>
> 属于此分类的元素有：`<h1>-<h6>` 和 `<hgroup>`。

#### 短语内容

> 短语内容（Phrasing content）是流式内容的一个子集，定义了文档中的文本和标记。短语内容的序列构成段落。
>
> 属于此类的元素有：

- `<abbr>`

- `<audio>`

- `<b>`

- `<bdi>`

- `<bdo>`

- `<br>`

- `<button>`

- `<canvas>`

- `<cite>`

- `<code>`

- `<data>`

- `<datalist>`

- `<dfn>`

- `<em>`

- `<embed>`

- `<i>`

- `<iframe>`

- `<img>`

- `<input>`

- `<kbd>`

- `<label>`

- `<mark>`

- `<math>`

- `<meter>`

- `<noscript>`

- `<object>`

- `<output>`

- `<picture>`

- `<progress>`

- `<q>`

- `<ruby>`

- `<s>`

- `<samp>`

- `<script>`

- `<select>`

- `<slot>`

- `<small>`

- `<span>`

- `<strong>`

- `<sub>`

- `<sup>`

- `<svg>`

- `<template>`

- `<textarea>`

- `<time>`

- `<u>`

- `<var>`

- `<video>`

- `<wbr>`

- 纯文本（仅当所包含的内容不完全为空白字符）

> 一些其他的元素也属于这个分类，但仅限于以下特殊情况：

- `<a>`，当它仅包含短语内容时

- `<area>`，当它为 `<map>` 元素的子元素时

- `<del>`，当它仅包含短语内容时

- `<ins>`，当它仅包含短语内容时

- `<link>`，若存在 `itemprop` 属性

- `<map>`，当它仅包含短语内容时

- `<meta>`，若存在 `itemprop` 属性

#### 嵌入内容

> 嵌入内容（Embedded content）是流式内容的一个子集，它导入另一种资源，或者将来自另一种标记语言或命名空间的内容插入到文档中。属于此类的元素有：

- `<audio>`

- `<canvas>`

- `<embed>`

- `<iframe>`

- `<img>`

- `<math>`

- `<object>`

- `<picture>`

- `<svg>`

- `<video>`

#### 交互内容

> 交互内容（Interactive content）是流式内容的一个子集，包含为用户交互而特别设计的元素。属于此类的元素有：

- `<button>`

- `<details>`

- `<embed>`

- `<iframe>`

- `<label>`

- `<select>`

- `<textarea>`

> 一些其他的元素也属于这个分类，但仅限于以下特殊情况：

- `<a>`，若存在 `href` 属性

- `<audio>`，若存在 `controls` 属性

- `<img>`，若存在 `usemap` 属性

- `<input>`，若 `type` 属性不处于隐藏（hidden）状态

- `<object>`，若存在 `usemap` 属性

- `<video>`，若存在 `controls` 属性

#### 可感知内容

> 当内容既不是空的也不是隐藏的时候，它就是可感知（palpable）的；它是被渲染的内容，是实质性的。以流式内容为模型的元素应该至少有一个节点是可感知的。

#### 表单相关内容

> 表单相关内容（Form-associated content）是流式内容的一个子集，包括有表单所有者（通过 **form** 属性暴露）的元素，可以在预期有流式内容的地方使用。表单所有者要么是容纳这些元素的 `<form>` 元素，要么是在 `form` 属性中指定其 id 的元素。

- `<button>`

- `<fieldset>`

- `<input>`

- `<label>`

- `<meter>`

- `<object>`

- `<output>`

- `<progress>`

- `<select>`

- `<textarea>`

> 此类包含了几个子类：

- 可列举的元素（listed）

    > 在 form.elements 和 fieldset.elements 集合中列举出的元素。包括 `<button>`、`<fieldset>`、`<input>`、`<object>`、`<output>`、`<select>` 和 `<textarea>`。

- 可标记的元素（labelable）

    > 可以与 `<label>` 相关联的元素。包括 `<button>`、`<input>`、`<meter>`、`<output>`、`<progress>`、`<select>` 和 `<textarea>`。

- 可提交的元素（submittable）

    > 包括当表单提交时可以用来组成表单数据的元素。包括 `<button>`、`<input>`、`<object>`、`<select>` 和 `<textarea>`。

- 可重置的元素（resettable）

    > 当表单重置时会被重置的元素。包括 `<input>`、`<output>`、`<select>` 和 `<textarea>`。

### 二级分类

> 这里还有一些你需要注意的二级分类元素。

#### 支持脚本元素

> 支持脚本元素（Script-supporting element）是不直接影响文档渲染输出的元素。相反，它们的作用是支持脚本，或者直接包含或指定脚本代码，或者指定将被脚本使用的数据。
>
> 支持脚本元素有：

- `<script>`
- `<template>`

### 透明内容模型

> 如果一个元素拥有透明内容（Transparent content）模型，即使将透明内容移除并使用子元素取代，其内容也必须构成有效的 HTML5。
>
> 例如，`<del>` 和 `<ins>` 是透明的：

```html
<p>
  我们认为以下真理是<del><em>神圣而不可否认</em></del
  ><ins>不言而喻</ins>的。
</p>
```

## 块级元素

> 在 CSS 中，参与块级布局的内容被称为**块级内容**（block-level content）。

## 行级元素

> 在 CSS 中，参与行内布局的内容被称为**行级内容**（inline-level content）。默认情况下，大多数文本、替换元素以及生成的内容都是行级的。

## 怪异模式和标准模式

> 浏览器采用了两种模式，用以把能符合新规范的网站和老旧网站区分开。

## HTML 中使用的日期与时间格式

> 使用这些格式的元素包含一些令用户选择或指定日期、时间或日期和时间的 `<input>` 和 `<ins>`、`<del>` 元素，它们的 `datetime` 属性指定了插入或删除内容的日期或日期和时间。

### 星期字符串

| 星期字符串 | 年份和星期数（日期区间） |
| :-: | :-: |
| 2001-W37 | 2001 年的第 37 周（2001 年 9 月 10-16 日） |

> 注意，年份和星期数都由前导零补齐长度，年份补齐至四位数，而星期数补齐至两位数。

### 月份字符串

| 月份字符串 | 年份和月 |
| :-: | :-: |
| 17310-09 | 17310 年 9 月 |

> 注意，每个年份至少为四位长度，少于四位的年份需要由前导零补齐位数。

### 日期字符串

| 日期字符串 | 日期表示 |
| :-: | :-: |
| 1993-11-01 | 1993 年 11 月 1 日 |

### 时间字符串

| 时间字符串 | 时间 |
| 00:00:30.75 | 上午 12:00:30.75（午夜后 30.75 秒） |

### 本地日期时间字符串

| 日期/时间字符串 | 标准化日期/时间字符串 | 实际日期和时间 |
| :-: | :-: | :-: |
| 1986-01-28T11:38:00.01 | 1986-01-28T11:38:00.01 | 1986 年 1 月 28 日，上午 11:38:00.01 |

### 全局日期时间字符串

#### 时间偏移字符串

| 全局日期时间字符串 | 实际全局日期时间 | 本初子午线的日期和时间 |
| :-: | :-: | :-: |
| 2005-06-07T00:00Z | UTC 时间，2005 年 6 月 7 日半夜 | 2005 年 6 月 7 日半夜 |
| 1789-08-22T12:30:00.1-04:00 | 1789 年 8 月 22 日下午 12:30 经过十分之一秒，东部夏令时（EDT） | 1789 年 8 月 22 日下午 4:30 经过十分之一秒 |
| 3755-01-01 00:00+10:00 | 3755 年 1 月 1 日半夜，澳大利亚东部标准时间（AEST） | 3754 年 12 月 31 日下午 2:00 |

## 约束验证

> HTML5 引入了表单相关的一些新机制：它为 `<input>` 元素和约束验证增加了一些新的语义类型，使得客户端检查表单内容变得容易。基本上，通过设置一些新的属性，常用的约束条件可以无需 JavaScript 代码而检测到；对于更复杂的约束条件的校验可以尝试使用约束验证 API。

### 固有和基本的约束

> 在 HTML 中，有两种方式声明基本的约束：

- 给 `<input>` 元素的 `type` 属性选择最合适的语义化的值，比如，选择 `email` 类型将会自动创建一个约束，用于检查输入的值是否是一个有效的电子邮件地址。

- 设置验证相关的属性值，允许用一种简单的方式来描述基本的约束，而不必要使用 JavaScript。

#### 语义的 input 类型

> `type` 属性中的固有约束有：

| Input 类型 | 约束描述 | 相关违约 |
| :-: | :-: | :-: |
| `<input type="URL">` | 值必须为 URL 现行标准定义的绝对 URL 地址。 | TypeMismatch 约束违反 |
| `<input type="email">` | 该值必须是一个语法上有效的电子邮件地址，其格式一般为 `username@hostname.tld`，但也可以是本地的，如 `username@hostname`。 | TypeMismatch 约束违反 |

#### 验证相关的属性

> 除了上面描述的 `type` 属性外，以下属性用于描述基本约束。

| 属性 | 支持该特性的 Input 类型 | 可接受的值 | 约束描述 | 相关违约 |
| :-: | :-: | :-: | :-: | :-: |
| `pattern` | `text`、`search`、`url`、`tel`、`email`、`password` | 一个JavaScript 正则表达式（以 `global`、`ignoreCase` 标志编译，且禁用了 `multiline` 标志） | 输入的值必须符合模式。 | `patternMismatch` 约束违反 |
| `min` | `range`、`number` `date`、`month`、`week` `datetime-local`、`time` | 一个有效的数字 一个有效的日期值 一个有效的日期时间值 | 输入的值必须大于等于该属性值。|  `rangeUnderflow` 约束违反 |
| `max` | `range`、`number` `date`、`month`、`week` `datetime-local`、`time` | 一个有效的数字 一个有效的日期值 一个有效的日期时间值 | 输入的值必须小于等于该属性值。 | `rangeOverflow` 约束违反 |
| `required` | `text`、`search`、`url`、`tel`、`email`、`password`、`date`、`datetime-local`、`month`、`week`、`time`、`number`、`checkbox`、`radio`、`file`；也在 `<select>` 和 `<textarea>` 元素上可用 | 由于是一个布尔属性，所以为 none：如果存在这个属性，则为 true；否则为 false | 如果指定了这个属性，则必须输入一个值。 | `valueMissing` 约束违反 |
| `step` | `date` `month` `week` `datetime-local、time` `range、number` | 一个代表天数的整数 一个代表月数的整数 一个代表周数的整数 一个代表秒数的整数 | 一个整数如果 `step` 没有设置为字面量 `any`，则输入值必须为 **min** + step 值的整数倍。 | `stepMismatch` 约束违反 |
| `minlength` | `text`、`search`、`url`、`tel`、`email`、`password`；也在 `<textarea>` 元素上可用 | 一个整数长度 | 如果输入值非空，则其字符数（码点）不得少于该属性的值。对于 `<textarea>`，所有换行符都被规范化为一个字符（相对于 CRLF 对）。 | `tooShort` 约束违反 |
| maxlength | `text`、`search`、`url`、`tel`、`email`、`password`；也在 `<textarea>` 元素上可用 | 一个整数长度 | 字符数（码点）不得超过该属性的值。 | `tooLong` 约束违反 |

### 约束验证过程

> 约束验证是通过约束验证 API 在单个表单元素上或在表单层面上，通过 `<form>` 元素本身完成。约束验证是通过以下方式完成的：

- 通过调用表单相关的 DOM 接口（`HTMLInputElement`、`HTMLSelectElement`、`HTMLButtonElement` 、`HTMLOutputElement` 或 `HTMLTextAreaElement`）的 `checkValidity()` 或 `reportValidity()` 方法，只对这个元素进行约束评估，允许脚本获得这些信息。`checkValidity()` 方法返回一个布尔值，表示该元素的值是否通过其约束（这通常是由用户代理在确定哪个 CSS 伪类，`:valid` 或 `:invalid` 适用时完成的）。相反，`reportValidity()` 方法会向用户报告任何约束失败的情况。

- 通过调用 `HTMLFormElement` 接口上的 `checkValidity()` 或 `reportValidity()` 方法。

- 通过提交表单本身。

> 调用 `checkValidity()` 也被称为约束的静态验证，调用 `reportValidity()` 也被称为约束的交互认证。

### 使用约束验证 API 进行复杂的约束

> 使用 JavaScript 和约束验证 API，可以实现更复杂的约束，例如，结合几个字段的约束，或涉及复杂计算的约束。

### 约束验证的可视化样式

#### 控制元素的外观

> 元素的外观可以通过 CSS 伪类进行控制。

- `:required`、`:optional` CSS 伪类

    > `:required` 和 `:optional` 伪类允许开发者编写选择器，以匹配有 required 属性或没有该属性的表单元素。

- `:placeholder-shown` CSS 伪类
    > 参见 `:placeholder-shown`。

- `:valid`、`:invalid` CSS 伪类

    > `:valid` 和 `:invalid` 伪类用于表示 `<input>` 元素，根据输入的类型设置，这些元素的内容分别可以验证和无法验证。这些类允许用户对有效或无效的表单元素进行样式设计，以使其更容易识别格式正确或不正确的元素。

#### 控制约束验证的文字

## 微数据

### 概要

> 微数据是 WHATWG HTML 标准的一部分，用于在网页上的现有内容中嵌套元数据。
>
> 从更高的角度来看，微数据由一组 name-value 对组成。这些组称为元素，每个 name-value 对都是一个属性。项目和属性由常规元素表示。

- 创建元素使用了 `itemscope` 属性。
- 向元素添加属性，`itemprop` 属性将用于其中一个元素的后代。

### 词汇表

> 谷歌和其他主要搜索引擎支持结构化数据的 `Schema.org` 词汇表。
>
> 微数据词汇表提供了 `Item` 的语义或含义。

### 本地化

> 在某些情况下，覆盖特定区域的搜索引擎可以提供微数据的本地特定扩展。

### 全局属性

- `itemid`——元素的唯一全局标识符。

- `itemprop`——用于向元素添加属性。每个 HTML 元素都可以指定一个 `itemprop` 属性，其中 `itemprop` 由一个名称和值对组成。

- `itemref`——不具有 `itemscope` 属性的元素的后代的属性可以使用 `itemref` 与元素相关联。`itemref` 提供了元素 `id` 列表（而不是一些 `itemid`）以及文档中其他位置的其他属性。

- `itemscope`——`itemscope`（通常）与 `itemtype` 一起使用，以指定块中包含的 HTML 是一个特定元素。`itemscope` 创建 `Item` 并定义与之关联的 `itemtype` 的范围。`itemtype` 是描述项及其属性上下文的词汇表（例如 schema.org）的有效 URL。

- `itemtype`——指定将用于在数据结构中定义 `itemprop`（元素属性）的词汇表的 URL。`itemscope` 用于设置数据结构中按 `itemtype` 设置的词汇表的有效范围。

## 微格式

> 微格式（microformat）是一种用于在 HTML 中嵌入语义和结构化数据的标准，它为社交网络应用程序、搜索引擎、聚合器和其他工具提供了一个 API。这些最小的 HTML 模式用于标记从基本到特定领域的信息实体，例如人物、组织、事件和地点。

- 要创建一个微格式对象，需要在 class 属性中使用 h-* 类名。

- 要给对象添加属性，需要在对象的后代元素上使用 p-*、u-*、dt-*、e-* 类名。

### 微格式的工作原理

> 网页的作者可以向他们的 HTML 中添加微格式。例如，如果他们想要标识自己的身份，可以使用 h-card 例如：

```html
<a class="h-card" href="https://alice.example.com">Alice Blogger</a>
```
