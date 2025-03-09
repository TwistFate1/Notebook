# JavaScript

## 什么是 JavaScript？

### 它到底可以做什么？

> 浏览器 API 内建于 web 浏览器中，它们可以将数据从周边计算机环境中筛选出来，还可以做实用的复杂工作。
>
> 第三方 API 并没有默认嵌入浏览器中，一般要从网上取得它们的代码和信息。

### 怎样向页面添加 JavaScript？

#### 内部 JavaScript

> 在结束标签 `</body>` 之前——添加以下内容：

```html
<script>
  // 在此编写 JavaScript 代码
</script>
```

> 通过把 JavaScript 放在底部，来确保所有的 HTML 元素完成加载。

#### 外部 JavaScript

> 在结束标签 `</head>` 之前添加以下内容（这样浏览器就能比在底部时更快开始加载文件）：

```html
<script type="module" src="script.js"></script>
```

#### 脚本加载策略

> 有几种不同的策略来确保 JavaScript 只在 HTML 解析之后运行：

- 在上面的内部 JavaScript 示例中，脚本元素放在文档正文的底部，因此只能在 HTML 正文的其他部分被解析以后运行。

- 在上面的外部 JavaScript 实例中，脚本元素放在文档的头部，在解析 HTML 正文之前解析。但是由于我们使用了 `<script type="module">`，代码被视为一个模块，并且浏览器在执行 JavaScript 模块之前会等待所有的 HTML 代码都处理完毕（也可以把外部脚本放在正文的底部，但是如果 HTML 内容较多且网络较慢，在浏览器开始获取并加载脚本之前可能需要大量的时间，因此将外部脚本放在头部通常会更好一些）。

- 如果仍然想在文档头部使用非模块脚本，可能阻塞整个页面的显示，并且可能出现错误，因为脚本在文档解析之前执行：

  - 对于外部脚本，应该在 `<script>` 元素上添加 `defer`（或者如果不需要 HTML 解析完成，则可以使用 `async`）属性。

  - 对于内部脚本，应该将代码封装在 `DOMContextLoaded` 事件监听器中。

### 注释

- 在双斜杠（`//`）后添加单行注释，比如：

```js
// 我是一条注释
```

- 在 `/*` 和 `*/` 之间添加多行注释，比如：

```js
/*
  我也是
  一条注释
*/
```

## 如何存储你需要的信息——变量

### 变量是什么？

> 一个变量，就是一个用于存放数值的容器。这个数值可能是一个用于累加计算的数字，或者是一个句子中的字符串。

### 声明变量

> 声明一个变量的语法是在 `var` 或 l`et` 关键字之后加上这个变量的名字：

```js
let myName;
let myAge;
```

### 初始化变量

> 在变量名之后跟上一个“=”，然后是数值：

```js
myName = "Chris";
myAge = 37;
```

### var 与 let 的区别

> var 声明，无论它们出现在脚本中的什么位置，都会在执行脚本中的任何代码之前进行处理。

### 更新变量

> 一旦变量赋值，你可以通过简单地给它一个不同的值来更新它。

#### 关于变量命名的规则

> "小写驼峰命名法"

### 变量类型

- Number

```js
let myAge = 17;
```

- String

```js
let dolphinGoodbye = "So long and thanks for all the fish";
```

- Boolean

```js
let iAmAlive = true;
```

- Array

```js
let myNameArray = ["Chris", "Bob", "Jim"];
let myNumberArray = [10, 15, 40];

myNameArray[0]; // should return 'Chris'
myNumberArray[2]; // should return 40
```

- Object

```js
let dog = { name: "Spot", breed: "Dalmatian" };

dog.name;
```

- 动态类型

```js
let myNumber = "500"; // oops, this is still a string
typeof myNumber;
myNumber = 500; // much better — now this is a number
typeof myNumber;
```

## JavaScript 中的基础数学 — 数字和操作符

### 算术运算符

> 加法 `+`、减法 `-`、乘法 `*`、除法 `/`、取余 `%`、幂 `**`。

#### 运算符优先级

#### 自增和自减运算符

> 使用增量（ `++` ）和递减（ `--` ）运算符来完成。

### 赋值运算符

> `=`、 `+=`、 `-=`、 `*=`、 `/=`。

### 比较运算符

> `===`、 `!==`、 `<`、 `>`、 `<=`、 `>=`。

## 文本处理——JavaScript 中的字符串

### 创建字符串

#### 单引号、双引号和反引号

```js
const single = '单引号';
const double = "双引号";
const backtick = `反引号`;

console.log(single);
console.log(double);
console.log(backtick);
```

> 使用反引号声明的字符串是一种特殊字符串，被称为模板字面量。在大多数情况下，模板字面量与普通字符串类似，但它具有一些特殊的属性：

- 你可以在其中嵌入 JavaScript

- 你可以声明多行的模板字面量

### 嵌入 JavaScript

> 在模板字面量中，你可以在 `${ }` 中包装 JavaScript 变量或表达式，其结果将被包含在字符串中：

```js
const name = "克里斯";
const greeting = `你好，${name}`;
console.log(greeting); // "你好，克里斯"
```

#### 使用“+”连接字符串

> 可以使用 `+` 运算符来连接普通字符串。

### 多行字符串

> 模板字符串会保留源代码中的换行符。
>
> 在字符串中包含换行字符（`\n`）。

## 函数

### 函数与方法

> 对象的成员函数被称为方法。

### 调用函数

```js
function myFunction() {
  alert("你好");
}

myFunction();
// 调用一次该函数
```

#### 函数参数

## 事件介绍

### 什么是事件？

> 事件是发生在你正在编程的系统中的事情——当事件发生时，系统产生（或“触发”）某种信号，并提供一种机制，当事件发生时，可以自动采取某种行动（即运行一些代码）。

### 使用 addEventListener()

```js
const btn = document.querySelector("button");

function random(number) {
  return Math.floor(Math.random() * (number + 1));
}

btn.addEventListener("click", () => {
  const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
});
```

#### 移除监听器

> 可以使用 `removeEventListener()` 方法再次删除它。

### 其他事件监听器机制

#### 事件处理器属性

> 可以触发事件的对象（如按钮）通常也有属性，其名称是 `on`，后面是事件的名称。

```js
const btn = document.querySelector("button");

function random(number) {
  return Math.floor(Math.random() * (number + 1));
}

btn.onclick = () => {
  const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
};
```

#### 内联事件处理器——不要使用

```html
<button onclick="bgChange()">按下我</button>
```

```js
function bgChange() {
  const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
}
```

### 事件对象

> 有时候在事件处理函数内部，你可能会看到一个固定指定名称的参数，例如 `event`、`evt` 或 `e`。这被称为事件对象，它被自动传递给事件处理函数，以提供额外的功能和信息。

#### 事件对象的额外属性

> 大多数事件对象都有一套标准的属性和方法。

### 阻止默认行为

## 冒泡

### 事件冒泡

> 事件冒泡描述了浏览器如何处理针对嵌套元素的事件。

#### 使用 stopPropagation() 修复问题

> Event 对象有一个可用的函数，叫做 `stopPropagation()`，当在一个事件处理器中调用时，可以防止事件向任何其他元素传递。

#### 事件捕获

> 事件传播的另一种形式是事件捕获。这就像事件冒泡，但顺序是相反的：事件不是先在最内层的目标元素上发生，然后在连续较少的嵌套元素上发生，而是先在最小嵌套元素上发生，然后在连续更多的嵌套元素上发生，直到达到目标。
>
> 事件捕获默认是禁用的，你需要在 `addEventListener()` 的 `capture` 选项中启用它。

### 事件委托

> 当我们想在用户与大量的子元素中的任何一个互动时运行一些代码时，我们在它们的父元素上设置事件监听器，让发生在它们身上的事件冒泡到它们的父元素上，而不必在每个子元素上单独设置事件监听器。

## DOM 脚本简介

### Web 浏览器的重要部分

- 窗口（window）是载入网页的浏览器标签；在 JavaScript 中，它由 `Window` 对象表示。使用这个对象上的方法，你可以做一些事情，比如返回窗口的大小（见 `Window.innerWidth` 和 `Window.innerHeight`），操作加载到窗口的文档，在客户端存储该文档的特定数据（例如使用本地数据库或其他存储机制），为当前窗口附加一个事件处理器等。

- 导航器（navigator）在网络上出现时，代表浏览器的状态和身份（即用户代理）。在 JavaScript 中，它由 `Navigator` 对象表示。你可以用这个对象来检索用户的首选语言、用户网络摄像头的媒体流等信息。

- 文档（document，在浏览器中用 DOM 表示）是加载到窗口的实际页面，在 JavaScript 中，它由 `Document` 对象表示。你可以使用这个对象来返回和操作构成文档的 HTML 和 CSS 的信息，例如，在 DOM 中获得一个元素的引用，改变其文本内容，对其应用新的样式，创建新的元素并将其作为子元素添加到当前元素中，甚至完全删除它。

### 文档对象模型

## 从服务器获取数据

### Fetch API

### XMLHttpRequest API

## 使用 JSON

### 什么是 JSON？

> JSON 是一种按照 JavaScript 对象语法的数据格式

#### JSON 结构

```json
{
  "squadName": "Super hero squad",
  "homeTown": "Metro City",
  "formed": 2016,
  "secretBase": "Super tower",
  "active": true,
  "members": [
    {
      "name": "Molecule Man",
      "age": 29,
      "secretIdentity": "Dan Jukes",
      "powers": ["Radiation resistance", "Turning tiny", "Radiation blast"]
    },
    {
      "name": "Madame Uppercut",
      "age": 39,
      "secretIdentity": "Jane Wilson",
      "powers": [
        "Million tonne punch",
        "Damage resistance",
        "Superhuman reflexes"
      ]
    },
    {
      "name": "Eternal Flame",
      "age": 1000000,
      "secretIdentity": "Unknown",
      "powers": [
        "Immortality",
        "Heat Immunity",
        "Inferno",
        "Teleportation",
        "Interdimensional travel"
      ]
    }
  ]
}
```

#### JSON 数组

```json
[
  {
    "name": "Molecule Man",
    "age": 29,
    "secretIdentity": "Dan Jukes",
    "powers": ["Radiation resistance", "Turning tiny", "Radiation blast"]
  },
  {
    "name": "Madame Uppercut",
    "age": 39,
    "secretIdentity": "Jane Wilson",
    "powers": [
      "Million tonne punch",
      "Damage resistance",
      "Superhuman reflexes"
    ]
  }
]
```
