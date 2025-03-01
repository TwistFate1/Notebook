# HTML

## 开始学习 HTML

### 什么是 HTML ？

> HTML（超文本标记语言——HyperText Markup Language）是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。
>
> HTML 使用“标记”（markup）来注明文本、图片和其他内容，以便于在 Web 浏览器中显示。
>
> HTML 元素通过“标签”（tag）将文本从文档中引出，标签由在“<”和“>”中包裹的元素名组成，HTML 标签里的元素名不区分大小写。

```html
<p>My cat is very grumpy</p>
```

### 剖析一个 HTML 元素

- 开始标签（Opening tag）：包含元素的名称，被左、右角括号所包围。开头标签标志着元素开始或开始生效的地方。

- 内容（Content）：元素的内容。

- 结束标签（Closing tag）：与开始标签相似，只是其在元素名之前包含了一个斜杠。这标志着该元素的结束。

> 整个元素即指开始标签、内容、结束标签三部分组成的整体。

#### 嵌套元素

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

#### 块级元素和内敛元素

- 块级元素在页面中以块的形式展现。一个块级元素出现在它前面的内容之后的新行上。任何跟在块级元素后面的内容也会出现在新的行上。块级元素通常是页面上的结构元素。

- 内联元素通常出现在块级元素中并环绕文档内容的一小部分，而不是一整个段落或者一组内容。内联元素不会导致文本换行。

#### 空元素

> 不是所有元素都拥有开始标签、内容和结束标签。一些元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西。这些元素被称为空元素。

### 属性

> 属性包含元素的额外信息，这些信息不会出现在实际的内容中。
>
> 属性必须包含：

- 一个空格，它在属性和元素名称之间。如果一个元素具有多个属性，则每个属性之间必须由空格分隔。

- 属性名称，后面跟着一个等于号。

- 一个属性值，由一对引号（""）引起来。

### 布尔属性

> 有时你会看到没有值的属性，这也是完全可以接受的。这些属性被称为布尔属性。布尔属性只能有一个值，这个值一般与属性名称相同。

```html
<!-- 使用 disabled 属性来防止终端用户输入文本到输入框中 -->
<input type="text" disabled />

<!-- 下面这个输入框不包含 disabled 属性，所以用户可以向其中输入 -->
<input type="text" />
```

### 剖析 HTML 文档

```html
<!doctype html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>
```

1. `<!DOCTYPE html>`: 声明文档类型。早期的 HTML（大约 1991-1992 年）文档类型声明类似于链接，规定了 HTML 页面必须遵从的良好规则，能自动检测错误和其他有用的东西。

2. `<html></html>`: `<html>` 元素。这个元素包裹了页面中所有的内容，有时被称为根元素。

3. `<head></head>`: `<head>` 元素。这个元素是一个容器，它包含了所有你想包含在 HTML 页面中但不在 HTML 页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述、CSS 样式、字符集声明等等。

4. `<meta charset="utf-8">`: `<meta>` 元素。这个元素代表了不能由其他 HTML 元相关元素表示的元数据，比如 `<base>`、`<link>`、`<script>`、`<style>` 或 `<title>`。charset 属性将你的文档的字符集设置为 UTF-8，其中包括绝大多数人类书面语言的大多数字符。有了这个设置，页面现在可以处理它可能包含的任何文本内容。没有理由不对它进行设置，它可以帮助避免以后的一些问题。

5. `<title></title>`: `<title>` 元素。这设置了页面的标题，也就是出现在该页面加载的浏览器标签中的内容。当页面被加入书签时，页面标题也被用来描述该页面。

6. `<body></body>`: `<body>` 元素。包含了你访问页面时所有显示在页面上的内容，包含文本、图片、视频、游戏、可播放音频轨道等等。

#### HTML 中的空白

> 无论你在 HTML 元素的内容中使用多少空格（包括一个或多个空白字符或换行），当渲染这些代码的时候，HTML 解释器会将连续出现的空白字符减少为一个单独的空格符。

### 实体引用：在 HTML 文档中包含特殊字符

> 在 HTML 中，字符 `<`、`>`、`"`、`'` 和 `&` 是特殊字符。

| 原义字符 | 等价字符引用 |
| :-: | :-: |
| < | `&lt;` |
| > | `&gt;` |
| " | `&quot;` |
| ' | `&apos;` |
| & | `&amp;` |

### HTML 注释

> 为了将一段 HTML 中的内容置为注释，你需要将其用特殊的记号 <!-- 和 --> 包裹起来，比如：

```html
<p>我在注释外！</p>

<!-- <p>我在注释内！</p> -->
```

## “头”里有什么——HTML 元信息

### 什么是 HTML 头部

> HTML 头部包含 HTML `<head>` 元素的内容，与 `<body>` 元素内容不同，页面在浏览器加载后它的内容不会在浏览器中显示，它的作用是保存页面的一些元数据。

#### 添加标题

> `<title>` 元素，它可以为文档添加标题。

### 元数据：`<meta>` 元素

#### 指定文档中的字符编码

```html
<meta charset="utf-8" />
```

### 在你的站点增加自定义图标

> 为了进一步丰富你的网站设计，你可以在元数据中添加对自定义图标的引用，它们会在某些场景下显示。最常见的用例为 **favicon**（为“favorites icon”的缩写，在浏览器的“收藏夹”及“书签”列表中显示）。

#### 为文档设定主语言

```html
<html lang="zh-CN">
  …
</html>
```

## HTML 文本处理基础

### 基础：标题和段落

> 在 HTML 中，每个段落是通过 `<p>` 元素标签进行定义的，比如下面这样：

```html
<p>我是一个段落，千真万确。</p>
```

> 每个标题（Heading）都必须被包裹在一个标题元素中：

```html
<h1>我是文章的标题</h1>
```

> 一共有六种标题元素标签——`h1`、`h2`、`h3`、`h4`、`h5` 和 `h6`。每个元素代表文档中不同级别的内容：`<h1>` 表示主标题，`<h2>` 表示二级子标题，`<h3>` 表示三级子标题，依此类推。

### 列表

#### 无序列表

```html
<ul>
  <li>豆浆</li>
  <li>油条</li>
  <li>豆汁</li>
  <li>焦圈</li>
</ul>
```

#### 有序列表

```html
<ol>
  <li>沿这条路走到头</li>
  <li>右转</li>
  <li>直行穿过第一个十字路口</li>
  <li>在第三个十字路口处左转</li>
  <li>继续走 300 米，学校就在你的右手边</li>
</ol>
```

#### 嵌套列表

> 将一个列表嵌入到另一个列表是完全可以的。

## 强调与重要性

### 什么是强调和着重强调？

#### 强调

> 在书面用语中，我们可以使用斜体字来达到同样的效果。
>
> 在 HTML 中我们用 `<em>`（emphasis）元素来标记这样的情况。

#### 着重强调

> 在书面用语中则是用粗体字来达到强调的效果。
>
> 在 HTML 中我们用 `<strong>`（strong importance）元素来标记这样的情况。

#### 斜体、粗体、下划线……

> 像这样仅仅影响表象而且没有语义的元素，被称为表现元素（presentational element）并且不应该再被使用。

- `<i>` 被用来传达传统上用斜体表达的意义：外国文字、分类名称、技术术语、思想……

- `<b>` 被用来传达传统上用粗体表达的意义：关键字、产品名称、引导句……

- `<u>` 被用来传达传统上用下划线表达的意义：专有名词、拼写错误……

## 文档与网络架构

### 文档的基本组成部分

- 页眉

    > 通常横跨于整个页面顶部有一个大标题 和/或 一个标志。这是网站的主要一般信息，通常存在于所有网页。

- 导航栏

    > 指向网站各个主要区段的超链接。通常用菜单按钮、链接或标签页表示。类似于标题栏，导航栏通常应在所有网页之间保持一致，否则会让用户感到疑惑，甚至无所适从。许多 web 设计人员认为导航栏是标题栏的一部分，而不是独立的组件，但这并非绝对；还有人认为，两者独立可以提供更好的 无障碍访问特性，因为屏幕阅读器可以更清晰地分辨二者。

- 主内容

    > 中心的大部分区域是当前网页大多数的独有内容，例如视频、文章、地图、新闻等。这些内容是网站的一部分，且会因页面而异。

- 侧边栏

    > 一些外围信息、链接、引用、广告等。通常与主内容相关（例如一个新闻页面上，侧边栏可能包含作者信息或相关文章链接），还可能存在其他的重复元素，如辅助导航系统。

- 页脚

    > 横跨页面底部的狭长区域。和标题一样，页脚是放置公共信息（比如版权声明或联系方式）的，一般使用较小字体，且通常为次要内容。还可以通过提供快速访问链接来进行 SEO。

> 为了实现语义化标记，HTML 提供了明确这些区段的专用标签，例如：

- `<header>`：页眉。

- `<nav>`：导航栏。

- `<main>`：主内容。主内容中还可以有各种子内容区段，可用`<article>`、`<section>` 和 `<div>` 等元素表示。

- `<aside>`：侧边栏，经常嵌套在 `<main>` 中。

- `<footer>`：页脚。

### HTML 布局元素细节

- `<main>` 存放每个页面独有的内容。每个页面上只能用一次 `<main>`，且直接位于 `<body>` 中。最好不要把它嵌套进其他元素。

- `<article>` 包围的内容即一篇文章，与页面其他部分无关（比如一篇博文）。

- `<section>` 与 `<article>` 类似，但 `<section>` 更适用于组织页面使其按功能（比如迷你地图、一组文章标题和摘要）分块。一般的最佳用法是：以 标题 作为开头；也可以把一篇 `<article>` 分成若干部分并分别置于不同的 `<section>` 中，也可以把一个区段 `<section>` 分成若干部分并分别置于不同的 `<article>` 中，取决于上下文。

- `<aside>` 包含一些间接信息（术语条目、作者简介、相关链接，等等）。

- `<header>` 是简介形式的内容。如果它是 `<body>` 的子元素，那么就是网站的全局页眉。如果它是 `<article>` 或`<section>` 的子元素，那么它是这些部分特有的页眉（此 `<header>` 非彼标题）。

- `<nav>` 包含页面主导航功能。其中不应包含二级链接等内容。

- `<footer>` 包含了页面的页脚部分。

#### 无语义元素

> HTML 提供了 `<div>` 和 `<span>` 元素。
>
> `<span>` 是一个内联的（inline）无语义元素，最好只用于无法找到更好的语义元素来包含内容时，或者不想增加特定的含义时。
>
> `<div>` 是一个块级无语义元素，应仅用于找不到更好的块级元素时，或者不想增加特定的意义时。

**注意：** `<div>` 元素非常容易被滥用。

### 换行与水平分割线

#### `<br>`：换行元素

> `<br>` 可在段落中进行换行；`<br>` 是唯一能够生成多个短行结构（例如邮寄地址或诗歌）的元素。

```html
<p>
  从前有个人叫小高<br />
  他说写 HTML 感觉最好<br />
  但他写的代码结构语义一团糟<br />
  他写的标签谁也懂不了。
</p>
```

#### `<hr>`：主题性中断元素

> `<hr>` 元素在文档中生成一条水平分割线，表示文本中主题的变化（例如话题或场景的改变）。

## 文本格式进阶

### 描述列表

> 标记一组项目及其相关描述，例如术语和定义，或者是问题和答案等。

```html
<dl>
  <dt>内心独白</dt>
  <dd>
    戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。
  </dd>
  <dt>语言独白</dt>
  <dd>
    戏剧中，某个角色把自己的想法直接进行念白表演，观众和其他角色都可以听到。
  </dd>
  <dt>旁白</dt>
  <dd>
    戏剧中，为渲染幽默或戏剧性效果而进行的场景之外的补充注释念白，只面向观众，内容一般都是角色的感受、想法、以及一些背景信息等。
  </dd>
</dl>
```

> 一个术语可以同时有多个描述。

### 引用

#### 块引用

> 如果一个块级内容（一个段落、多个段落、一个列表等）从其他地方被引用，你应该把它用 `<blockquote>` 元素包裹起来表示，并且在 `cite` 属性里用 URL 来指向引用的资源。

```html
<p>Here is a blockquote:</p>
<blockquote
  cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote">
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>
```

#### 行内引用

> 除了使用 `<q>` 元素以外，行内元素用同样的方式工作。

```html
<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/q"
    >intended for short quotations that don't require paragraph breaks.</q
  >
</p>
```

> 浏览器默认将其作为普通文本放入引号内表示引用。

#### 引文

```html
<p>
  According to the
  <a href="/zh-CN/docs/Web/HTML/Element/blockquote">
    <cite>MDN blockquote page</cite></a
  >:
</p>

<blockquote
  cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote">
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>

<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q cite="https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/q"
    >intended for short quotations that don't require paragraph breaks.</q
  >
  — <a href="/zh-CN/docs/Web/HTML/Element/q"> <cite>MDN q page</cite></a
  >.
</p>
```

### 缩略语

> `<abbr>`——它常被用来包裹一个缩略语或缩写，并且提供缩写的解释。

```html
<p>
  我们使用
  <abbr title="超文本标记语言（Hyper text Markup Language）">HTML</abbr>
  来组织网页文档。
</p>

<p>
  第 33 届<abbr title="夏季奥林匹克运动会">奥运会</abbr>已于 2024 年 7
  月在法国巴黎举行。
</p>
```

#### 标记联系方式

> HTML 有个用于标记联系方式的元素——`<address>`。它仅仅包含联系方式，例如：

```html
<address>Chris Mills, Manchester, The Grim North, UK</address>
```

#### 上标和下标

> 当你使用日期、化学方程式、和数学方程式时会偶尔使用上标和下标，以确保它们的正确含义。`<sup>` 和 `<sub>` 元素可以解决这样的问题。例如：

```html
<p>
  咖啡因的化学方程式是 C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>。
</p>
<p>如果 x<sup>2</sup> 的值为 9，那么 x 的值必为 3 或 -3。</p>
```

#### 展示计算机代码

> 有大量的 HTML 元素可以来标记计算机代码：

- `<code>`：用于标记计算机通用代码。

- `<pre>`：用于保留空白字符（通常用于代码块）——如果文本中使用了缩进或多余的空白，浏览器将忽略它，你将不会在呈现的页面上看到它。但是，如果你将文本包含在 `<pre></pre>` 标签中，那么空白将会以与你在文本编辑器中看到的相同的方式渲染出来。

- `<var>`：用于标记具体变量名。

- `<kbd>`：用于标记输入电脑的键盘（或其他类型）输入。

- `<samp>`：用于标记计算机程序的输出。

```html
<pre><code>const para = document.querySelector('p');

para.onclick = function() {
  alert('噢，噢，噢，别点我了。');
}</code></pre>

<p>
  请不要使用 <code>&lt;font&gt;</code> 、
  <code>&lt;center&gt;</code> 等表象元素。
</p>

<p>在上述的 JavaScript 示例中，<var>para</var> 表示一个段落元素。</p>

<p>按 <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd> 选择全部内容。</p>

<pre>$ <kbd>ping mozilla.org</kbd>
<samp>PING mozilla.org (63.245.215.20): 56 data bytes
64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
```

#### 标记时间和日期

> HTML 还支持将时间和日期标记为可供机器识别的格式的 `<time>` 元素，例如：

```html
<!-- 标准简单日期 -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- 只包含年份和月份-->
<time datetime="2016-01">January 2016</time>
<!-- 只包含月份和日期 -->
<time datetime="01-20">20 January</time>
<!-- 只包含时间，小时和分钟数 -->
<time datetime="19:30">19:30</time>
<!-- 还可包含秒和毫秒 -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- 日期和时间 -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- 含有时区偏移值的日期时间 -->
<time datetime="2016-01-20T19:30+01:00"
  >7.30pm, 20 January 2016 is 8.30pm in France</time
>
<!-- 提及特定周 -->
<time datetime="2016-W04">The fourth week of 2016</time>
```

## 创建超链接

### 什么是超链接？

> 超链接使我们能够将我们的文档链接到任何其他文档（或其他资源），也可以链接到文档的指定部分，我们可以在一个简单的网址上提供应用程序。

### 链接的解析

> 通过将文本或其他内容包裹在 `<a>` 元素内，并给它一个包含网址的 `href` 属性（也称为超文本引用或目标，它将包含一个网址）来创建一个基本链接。

```html
<p>
  我创建了一个指向
  <a href="https://www.mozilla.org/zh-CN/">Mozilla 主页</a>的链接。
</p>
```

#### 块级链接

> 任何内容，甚至块级元素都可以作为链接出现。如果想让标题元素变为链接，就把它包裹在锚点元素（`<a>`）内，像这个代码段一样：

```html
<a href="https://developer.mozilla.org/zh-CN/">
  <h1>MDN Web 文档</h1>
</a>
<p>自从 2005 年起，就开始记载包括 CSS、HTML、JavaScript 等网络技术。</p>
```

#### 图片链接

> 如果有需要作为链接的图片，使用 `<a>` 元素来包裹要引用图片的 `<img>` 元素。下面的示例使用相对路径来引用本地存储的 SVG 图像文件。

```html
<a href="https://developer.mozilla.org/zh-CN/">
  <img src="mdn_logo.svg" alt="MDN Web 文档" />
</a>
```

#### 使用 title 属性添加支持信息

> 你可能要添加到你的链接的另一个属性是 `title`。这旨在包含关于链接的补充信息，例如页面包含什么样的信息或需要注意的事情。

```html
<p>
  我创建了一个指向
  <a
    href="https://www.mozilla.org/zh-CN/"
    title="了解 Mozilla 使命以及如何参与贡献的最佳站点。">
    Mozilla 主页</a
  >的超链接。
</p>
```

### 统一资源定位符（URL）与路径（path）快速入门

> 统一资源定位符（Uniform Resource Locator，URL）是一个定义了在网络上的位置的一个文本字符串。

- **指向当前目录**：如果你想在 `index.html`（顶层 `index.html`）中包含一个指向 `contacts.html` 的超链接，你只需要指定想要链接到的文件名。因为它与当前文件是在同一个目录的，所以你应该使用的 URL 是 `contacts.html`：

```html
<p>
  要联系某位工作人员，请访问我们的<a href="contacts.html">联系人页面</a>。
</p>
```

- **指向子目录**：如果你想在 `index.html` （顶层 `index.html`）中包含一个指向 `projects/index.html` 的超链接，你需要先进入 `projects` 项目目录，然后通过指定目录的名称，然后是正斜杠，然后是文件的名称指明要链接到的文件 `index.html`。因此你要使用的 URL 是 `projects/index.html`：

```html
<p>请访问我的<a href="projects/index.html">项目主页</a>。</p>
```

- **指向上级目录**：如果你想在 `projects/index.html` 中包含一个指向 `pdfs/project-brief.pdf` 的超链接，你必须先返回上级目录，然后再回到 `pdfs` 目录。“返回上一个目录级”使用两个英文点号表示（`..`），因此你应该使用的 URL 是 `../pdfs/project-brief.pdf`：

```html
<p>点击打开<a href="../pdfs/project-brief.pdf">项目简介</a>。</p>
```

#### 文档片段

> 超链接除了可以链接到文档外，也可以链接到 HTML 文档的特定部分（被称为文档片段）。要做到这一点，你必须首先给要链接到的元素分配一个 `id` 属性。通常情况下，链接到一个特定的标题是有意义的，这看起来就像下面这样：

```html
<h2 id="Mailing_address">邮寄地址</h2>
```

> 为了链接到那个特定的 `id`，要将它放在 URL 的末尾，并在前面包含井号（`#`），例如：

```html
<p>
  要提供意见和建议，请将信件邮寄至<a href="contacts.html#Mailing_address"
    >我们的地址</a
  >。
</p>
```

> 你甚至可以在同一份文档下，通过链接文档片段，来链接到当前文档的另一部分：

```html
<p>本页面底部可以找到<a href="#Mailing_address">公司邮寄地址</a>。</p>
```

#### 绝对 URL 和相对 URL

- **绝对 URL**：指向由其在 Web 上的绝对位置定义的位置，包括协议和域名。像下面的例子，如果 `index.html` 页面上传到了 `projects` 这一个目录。并且 `projects` 目录位于 web 服务站点的根目录，web 站点的域名为 `https://www.example.com`，那么这个页面就可以通过 `https://www.example.com/projects/index.html` 访问（或者通过 `https://www.example.com/projects/` 来访问，因为在没有指定特定的 URL 的情况下，大多数 web 服务器会默认访问加载 `index.html` 这类页面）

- **相对 URL**：指向与你链接的文件相关的位置，更像我们在前面一节中所看到的位置。例如，如果我们想从示例文件链接 `https://www.example.com/projects/index.html` 转到相同目录下的一个 PDF 文件，URL 就是文件名（例如 `project-brief.pdf`），没有其他的信息要求。如果 PDF 文件能够在 `projects` 的子目录 `pdfs` 中访问到，相对路径就是 `pdfs/project-brief.pdf`（对应的绝对 URL 是 `https://www.example.com/projects/pdfs/project-brief.pdf`）

### 链接最佳实践

#### 使用清晰的链接措辞

```html
<p><a href="https://www.mozilla.org/zh-CN/firefox/">下载 Firefox </a></p>
```

- 不要重复 URL 作为链接文本的一部分——URL 看起来很丑，当屏幕阅读器一个字母一个字母的读出来的时候听起来就更丑了。

- 不要在链接文本中说“链接”或“链接到”——它只是无用的内容。屏幕阅读器告诉人们有一个链接。可视化用户也会知道有一个链接，因为链接通常是用不同的颜色设计的，并且存在下划线（这个惯例一般不应该被打破，因为用户习惯了它）。

- 保持你的链接标签尽可能短——这非常重要，因为屏幕阅读器需要解释整个链接文本。

- 尽量减少相同文本的多个副本链接到不同地方的情况。如果存在标记为“单击此处”、“单击此处”、“单击此处”这样脱离上下文的链接文本，容易对使用屏幕阅读器的用户带来问题。

#### 链接到非 HTML 资源——留下清晰的指示

> 当链接到一个需要下载的资源（如 PDF 或 Word 文档）或流媒体（如视频或音频）或有另一个潜在的意想不到的效果（打开一个弹出窗口），你应该添加明确的措辞，以减少混乱。

#### 在下载链接时使用 download 属性

> 当你链接到要下载的资源而不是在浏览器中打开时，你可以使用 download 属性来提供一个默认的保存文件名。下面是一个 Firefox 的 Windows 最新版本下载链接的示例：

```html
<a
  href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
  download="firefox-latest-64bit-installer.exe">
  下载最新的 Firefox 中文版 - Windows（64 位）
</a>
```

### 电子邮件链接

> 当点击一个链接或按钮时，可能会开启新的邮件的发送而不是连接到一个资源或页面。这种场景可以使用 `<a>` 元素和 `mailto:` URL 协议实现。

## HTML 中的图片

### 怎样将图片放到网页上？

> 要想在网页上放置简单的图像，我们需要使用 `<img>` 元素。这个元素是空元素（即无法包含任何子内容和结束标签），它需要两个属性才能起作用：`src` 和 `alt`。`src` 属性包含一个 URL，该 URL 指向要嵌入页面的图像。`src` 属性可以是相对 URL 或绝对 URL，这与 `<a>` 元素的 `href` 属性类似。如果没有 `src` 属性，`img` 元素就没有图像可加载。

```html
<img src="images/dinosaur.jpg" alt="恐龙" />
```

#### 备选文本

> `alt` 的值应该是图片的文本描述，用于在图片无法显示或者因为网速慢而加载缓慢的情况下使用。

#### 宽度和高度

> 你可以用 `width` 和 `height` 属性来指定你的图片的宽度和高度。它们的值是不带单位的整数，以像素为单位表示图像的宽度和高度。
>
> 你页面的 HTML 和图片是分开的资源，由浏览器用相互独立的 HTTP(S) 请求来获取。一旦浏览器接收到 HTML，它就会开始将其显示给用户。如果图片尚未接收到（通常会是这种情况，因为图片文件的大小通常比 HTML 文件大得多），那么浏览器将只渲染 HTML，并在图片接收到后立即更新页面。

#### 图片标题

> 你可以通过给图片增加 `title` 属性来提供更多的信息。

### 媒体资源和许可

> 你在网络上找到的图像（以及其他媒体资源类型）都以不同的许可类型发布。在你构建的网站上使用图像之前，请确保你拥有该图像的所有权、获得使用许可或遵守所有者的许可条件。

#### 了解许可类型

- 版权所有

- 自由许可

- 公共领域/CC0

### 通过为图片搭配说明文字的方式来解说图片

> 使用 HTML 的 `<figure>` 和 `<figcaption>` 元素，它正是为此而被创造出来的：为图片提供一个语义容器，在说明文字和图片之间建立清晰的关联。

```html
<figure>
  <img
    src="images/dinosaur.jpg"
    alt="The head and torso of a dinosaur skeleton;
            it has a large head with long sharp teeth"
    width="400"
    height="341" />

  <figcaption>
    A T-Rex on display in the Manchester University Museum.
  </figcaption>
</figure>
```

### CSS 背景图片

> CSS 属性 `background-image` 和其他的 `background-*` 属性是用来控制背景图片的。比如，要想为页面中的每个段落设置一个背景图片，你可以这样做：

```css
p {
  background-image: url("images/dinosaur.jpg");
}
```

### 网页上的其他图形

- Canvas

    > `<canvas>` 元素提供了使用 JavaScript 绘制 2D 图形的 API。

- SVG

    > 你可以借助可缩放矢量图形（SVG）来使用线条、曲线和其他几何形状来渲染 2D 图形。借助矢量图形，你可以创建能够以任意尺寸清晰缩放的图像。

- WebGL

    > WebGL API 指南将帮助你入门 WebGL，这是用于 Web 的 3D 图形 API，可让你在 Web 内容中使用标准的 OpenGL ES。

- 使用 HTML 音频和视频

    > 与 `<img>` 类似，你可以使用 HTML 将 `<video>` 和 `<audio>` 嵌入到网页中，并控制其播放。

- WebRTC

    > WebRTC 中的 RTC 代表实时通信（Real-Time Communications），这是一种可以在浏览器客户端（对等方）之间进行音频/视频流和数据共享的技术。

## 视频和音频内容

### web 中的音频和视频

> 最早的在线视频和音频的流行得益于专有的基于插件的技术，如 `Flash` 和 `Silverlight`。这两种技术存在安全性和无障碍问题，现已过时，取而代之的是原生的 HTML 解决方案，该解决方案包括 `<video>` 和 `<audio>` 元素以及用于控制它们的 `JavaScript API`。

#### `<video>` 元素

```html
<video src="rabbit320.webm" controls>
  <p>
    你的浏览器不支持 HTML 视频。可点击<a href="rabbit320.mp4">此链接</a>观看。
  </p>
</video>
```

- `src`

    > 同 `<img>` 元素的使用方式相同，`src`（来源）属性指向你想要嵌入到网页中的视频资源，它们的运作方式完全相同。

- `controls`

    > 你必须使用 controls 属性来让视频或音频包含浏览器自带的控制界面，或者使用适当的 `JavaScript API` 构建自己的界面。至少，界面必须包括启动和停止媒体以及调整音量的方法。

- `<video>` 元素内的段落

    > 这个叫做后备内容，当浏览器不支持 `<video>` 元素的时候，就会显示这段内容，借此我们能够对旧的浏览器提供回退。你可以添加任何后备内容，在这个例子中我们提供了一个指向这个视频文件的链接，从而使用户至少可以访问到这个文件，而不会局限于浏览器的支持。

#### 使用多个播放源以提高兼容性

> 像 MP3、MP4 还有 WebM 这些格式叫做容器格式。

#### 浏览器所支持的媒体文件

```html
<video controls>
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>你的浏览器不支持此视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>
</video>
```

> 浏览器会检查 `<source>` 元素，并且播放第一个与其自身 codec 相匹配的媒体。

#### 其他 `<video>` 特性

- `width` 和 `height`

    > 你可以用属性控制视频的尺寸，也可以用 CSS 来控制视频尺寸。无论使用哪种方式，视频都会保持它原始的长宽比——也叫做纵横比。如果你设置的尺寸没有保持视频原始长宽比，那么视频边框将会拉伸，而未被视频内容填充的部分，将会显示默认的背景颜色。

- autoplay

    > 这个属性会使音频和视频内容立即播放，即使页面的其他部分还没有加载完全。建议不要在你的网站上自动播放视频（或音频），因为用户可能会反感。

- loop

    > 这个属性可以让视频（或者音频）文件在结束时再次开始播放。这个也可能很恼人，同样不建议使用，除非有必要。

- muted

    > 这个属性会导致媒体播放时，默认关闭声音。

- poster

    > 这个属性指向了一个图像的 URL，这个图像会在视频播放前显示。通常用于粗略的预览或者广告。

- preload

    > 这个属性被用来缓冲较大的文件，有三个值可选：
  - "none"：不缓冲文件

  - "auto"：页面加载后缓存媒体文件
  
  - "metadata"：仅缓冲文件的元数据

#### `<audio>` 元素

> `<audio>` 元素与 `<video>` 元素的使用方式几乎完全相同，只有一些细微的差别。
>
> 其他一些 HTML `<audio>` 与 `<video>` 的差异如下：

- `<audio>` 元素不支持 `width/heigth` 属性——由于其并没有视觉部件，也就没有内容要设置 `width/height`。

- 它同时也不支持 `poster` 属性——同样，因为没有视觉部件。

#### 显示视频文本

> 只需使用 `WebVTT` 文件格式和 `<track>` 元素即可。
>
> WebVTT 是一个格式，用来编写文本文件，这个文本文件包含了众多的字符串，这些字符串会带有一些元数据，它们可以用来描述这个字符串将会在视频中显示的时间，甚至可以用来描述这些字符串的样式以及定位信息（尽管有限制）。这些字符串叫做 **cue** ，你可以根据不同的需求来显示不同类型的 cue，最常见的如下：

- subtitles

    > 外语材料的翻译字幕，来帮助那些听不懂音频中说的什么的人理解音频当中的内容。

- captions
    > 同步翻译对白，或是描述一些有重要信息的声音，来帮助那些不能听音频的人理解音频中的内容。

- 定时描述

    >由媒体播放器朗读的文本，其向盲人或其他视力受损用户描述重要的视觉内容。

> 一个典型的 WebVTT 文件如下：

```vtt
WEBVTT

1
00:00:22.230 --> 00:00:24.606
第一段字幕

2
00:00:30.739 --> 00:00:34.074
第二段

...
```

```html
<video controls>
  <source src="example.mp4" type="video/mp4" />
  <source src="example.webm" type="video/webm" />
  <track kind="subtitles" src="subtitles_es.vtt" srclang="es" label="Spanish" />
</video>
```

## HTML 表格基础

### 什么是表格？

> 表格是由行和列（**表格数据**）组成的结构化数据集，它让你快速简单地查找某个表示不同类型数据之间的某种关系的值。

#### 表格如何工作？

> 表格的一个特点就是固定不变。通过在行标题和列标题之间建立视觉关联，信息可以容易地被解读。

#### 表格风格

> 优秀的表格风格可读性更好。

### 创建表格

> `<table>`为表格，使用 `tr` 和 `td` 创建表格行和单元格。

```html
<table>
  <tr>
    <td>我是第一个单元格</td>
    <td>我是第二个单元格</td>
    <td>我是第三个单元格</td>
    <td>我是第四个单元格</td>
  </tr>

  <tr>
    <td>第二行，第一个单元格</td>
    <td>单元格 2</td>
    <td>单元格 3</td>
    <td>单元格 4</td>
  </tr>
</table>
```

### 使用 `<th>` 元素添加标题

> 使用 `<th>` 元素标记标题。

### 允许单元格跨越多行和列

> 表格中的标题和单元格有 `colspan` 和 `rowspan` 属性可以实现横跨和竖跨。

### 为表格中的列提供共同的样式

> 为整列数据的定义样式信息的方法：就是 `<col>` 和 `<colgroup>` 元素。

#### 使用 `<col>` 应用样式

```html
<table>
  <colgroup>
    <col />
    <col style="background-color: yellow" />
  </colgroup>
  <tr>
    <th>数据 1</th>
    <th>数据 2</th>
  </tr>
  <tr>
    <td>加尔各答</td>
    <td>橙汁</td>
  </tr>
  <tr>
    <td>机器人</td>
    <td>爵士乐</td>
  </tr>
</table>
```

> 定义了两个“样式列”，其中一个为第二列每列指定样式信息。没有为第一列设计样式，但仍必须包含一个空白的 `<col>` 元素，否则样式将只应用于第一列。
>
> 如果想将样式信息应用于两列，只需包含一个带有 `span` 属性的 `<col>` 元素即可，就像这样:

```html
<colgroup>
  <col style="background-color: yellow" span="2" />
</colgroup>
```

## HTML 表格进阶特性和无障碍

### 使用 `<caption>` 为你的表格增加一个标题

> 你可以通过 `<caption>` 元素为你的表格增加一个标题，再把 `<caption>` 元素放入 `<table>` 元素中。你应该把它放在 `<table>` 开始标签的下面。

```html
<table>
  <caption>
    侏罗纪时期的恐龙
  </caption>

  ...
</table>
```

### 添加 `<thead>`、`<tbody>` 和 `<tfoot>` 结构

- `<thead>` 元素必须包住表格的表头部分。一般是第一行，往往都是每列的标题，但是不是每种情况都是这样的。如果你使用了 `<col>/<colgroup>` 元素，那么 `<thead>` 元素就需要放在它们的下面。

- `<tbody>` 元素需要包住表格内容的主要部分（不是表头和表尾）。

- `<tfoot>` 元素需要包住表格的表尾部分。一般是最后一行，往往是对前面所有行的总结。
