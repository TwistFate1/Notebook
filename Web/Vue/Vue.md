# Vue

## 开始

### 简介

#### 什么是 Vue

> Vue是一款用于构建用户界面的 JavaScript 框架。

#### 渐进式框架

- 无需构建步骤，渐进式增强静态的 HTML
- 在任何页面中作为 Web Components 嵌入
- 单页应用 (SPA)
- 全栈 / 服务端渲染 (SSR)
- Jamstack / 静态站点生成 (SSG)
- 开发桌面端、移动端、WebGL，甚至是命令行终端中的界面

#### 单文件组件

> 将一个组件的逻辑 (JavaScript)，模板 (HTML) 和样式 (CSS) 封装在同一个文件里。

#### API 风格

> **选项式**和**组合式**。

### 快速上手

#### 创建一个应用

> 利用 Node.js 完成搭建。

```bash
npm create vue@latest
```

> 发布到环境。

```bash
npm run buiild
```

#### 通过 CDN 使用 Vue

**注意：** 将无法使用单文件组件 (SFC) 语法。

```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

## 基础

### 创建一个 Vue 应用

#### 应用实例

> Vue 应用通过 `createApp` 函数创建实例。

```js
import { createApp } from 'vue'

const app = createApp({
  /* 根组件选项 */
})
```

#### 根组件

> 传入 `creatApp` 的对象实际上是一个组件，每个应用需要一个根组件，其他组件将作为子组件。

```js
import { createApp } from 'vue'
// 从一个单文件组件中导入根组件
import App from './App.vue'

const app = createApp(App)
```

#### 挂载应用

> 应用实例必须在调用了 `.mount()` 方法后才会渲染出来。

```html
<div id="app"></div>
```

```js
app.mount('#app')
```

#### 应用配置

> 应用实例会暴露一个 `.config` 对象允许我们配置一些应用级的选项。

#### 多个应用实例

> `createApp` API 允许你在同一个页面中创建多个共存的 Vue 应用，而且每个应用都拥有自己的用于配置和全局资源的作用域。

---

### 模板语法

> 模板会进行编译优化。

#### 文本插值

> 最基本的数据绑定形式是文本插值，它使用的是双大括号（双向绑定）：

```html
<span>Message: {{ msg }}</span>
```

#### 原始 HTML

> 双大括号会将数据解释为纯文本，而不是 HTML。若想插入 HTML，需要使用 `v-html` 指令。

**注意：** 尽量避免动态渲染，会导致 XSS 漏洞。

#### Attribute 绑定

> 双大括号不能在 HTML attributes 中使用。想要响应式地绑定一个 attribute，应该使用 `v-bind` 指令：

```html
<div v-bind:id="dynamicId"></div>
```

> 如果绑定的值是 null 或者 undefined，那么该 attribute 将会从渲染的元素上移除。

#### 简写

> v-bind 的特殊简写语法：

```html
<div :id="dynamicId"></div>
```

#### 同名简写

> 如果 attribute 的名称与绑定的 JavaScript 值的名称相同，那么可以进一步简化语法，省略 attribute 值：

```html
<!-- 与 :id="id" 相同 -->
<div :id></div>

<!-- 这也同样有效 -->
<div v-bind:id></div>
```

#### 动态绑定多个值

```js
data() {
  return {
    objectOfAttrs: {
      id: 'container',
      class: 'wrapper'
    }
  }
}
```

> 通过不带参数的 `v-bind`，你可以将它们绑定到单个元素上:

```html
<div v-bind="objectOfAttrs"></div>
```

#### 使用 JavaScript 表达式

```html
{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div :id="`list-${id}`"></div>
```

#### 指令 Directives

> 完整的指令语法：`v-on:submit.prevent="onSubmit"`

---

### 响应式基础

#### 声明响应式状态

> 用 data 来声明：

```js
export default {
  data() {
    return {
      count: 1
    }
  },

  // `mounted` 是生命周期钩子，之后我们会讲到
  mounted() {
    // `this` 指向当前组件实例
    console.log(this.count) // => 1

    // 数据属性也可以被更改
    this.count = 2
  }
}
```

#### 声明方法

> 用 methods 选项:

```js
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  },
  mounted() {
    // 在其他方法或是生命周期中也可以调用方法
    this.increment()
  }
}
```

> 避免使用箭头函数，无法访问 `this` 。
>
> 在模板上使用：

```html
<button @click="increment">{{ count }}</button>
```

> DOM 更新不是同步的。

### 计算属性

#### 基础示例

```js
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      }
    }
  },
  computed: {
    // 一个计算属性的 getter
    publishedBooksMessage() {
      // `this` 指向当前组件实例
      return this.author.books.length > 0 ? 'Yes' : 'No'
    }
  }
}
```

```html
<p>Has published books:</p>
<span>{{ publishedBooksMessage }}</span>
```

#### 可写计算属性

> 通过同时提供 getter 和 setter 来创建：

```js
export default {
  data() {
    return {
      firstName: 'John',
      lastName: 'Doe'
    }
  },
  computed: {
    fullName: {
      // getter
      get() {
        return this.firstName + ' ' + this.lastName
      },
      // setter
      set(newValue) {
        // 注意：我们这里使用的是解构赋值语法
        [this.firstName, this.lastName] = newValue.split(' ')
      }
    }
  }
}
```

#### 获取上一个值

> 通过访问计算属性的 getter 的第一个参数来获取计算属性返回的上一个值：

```js
export default {
  data() {
    return {
      count: 2
    }
  },
  computed: {
    // 这个计算属性在 count 的值小于或等于 3 时，将返回 count 的值。
    // 当 count 的值大于等于 4 时，将会返回满足我们条件的最后一个值
    // 直到 count 的值再次小于或等于 3 为止。
    alwaysSmall(previous) {
      if (this.count <= 3) {
        return this.count
      }

      return previous
    }
  }
}
```

### 类与样式绑定

#### 绑定 HTML 样式

> `:class` 传递一个对象或数组来动态切换类：

```html
<div :class="{ active: isActive }"></div>
```

#### 绑定内敛样式

> `:style` 支持绑定 JavaScript 对象值，对应的是 HTML 元素的 style 属性。

### 条件渲染

#### v-if

> `v-if` 指令用于条件性地渲染一块内容。这块内容只会在指令的表达式返回真值时才被渲染。

```html
<h1 v-if="awesome">Vue is awesome!</h1>
```

#### v-else

> 使用 `v-else` 为 `v-if` 添加一个“else 区块”。

```html
<button @click="awesome = !awesome">Toggle</button>

<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```

#### v-else-if

> `v-else-if` 提供的是相应于 `v-if` 的“else if 区块”。

```html
<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
```

> 均可以在 `<template>` 元素上使用。
>
> `v-show` 始终渲染（频繁切换时使用），只改变该元素的 CSS 属性。

### 列表渲染

#### v-for

> `v-for` 基于一个数组来渲染一个列表。

```js
data() {
  return {
    items: [{ message: 'Foo' }, { message: 'Bar' }]
  }
}
```

```html
<li v-for="item in items">
  {{ item.message }}
</li>
```

> 可以使用 `of` 作为分隔符来替代 `in`。

```html
<div v-for="item of items"></div>
```

#### 通过 key 管理状态

> 重新排序而不是就地更新。

```html
<div v-for="item in items" :key="item.id">
  <!-- 内容 -->
</div>
```

#### 数组变化侦测

> 避免变更原数组。

### 事件处理

#### 监听事件

> `v-on` （简写为 `@` ）来监听事件，并在事件触发时执行 JavaScript 代码。

#### 内联事件处理器

```js
data() {
  return {
    count: 0
  }
}
```

```html
<button @click="count++">Add 1</button>
<p>Count is: {{ count }}</p>
```

#### 方法事件处理器

```js
data() {
  return {
    name: 'Vue.js'
  }
},
methods: {
  greet(event) {
    // 方法中的 `this` 指向当前活跃的组件实例
    alert(`Hello ${this.name}!`)
    // `event` 是 DOM 原生事件
    if (event) {
      alert(event.target.tagName)
    }
  }
}
```

```html
<!-- `greet` 是上面定义过的方法名 -->
<button @click="greet">Greet</button>
```

#### 在内联处理器中调用方法

```js
methods: {
  say(message) {
    alert(message)
  }
}
```

```html
<button @click="say('hello')">Say hello</button>
<button @click="say('bye')">Say bye</button>
```

#### 在内联事件处理器中访问事件参数

```html
<!-- 使用特殊的 $event 变量 -->
<button @click="warn('Form cannot be submitted yet.', $event)">
  Submit
</button>

<!-- 使用内联箭头函数 -->
<button @click="(event) => warn('Form cannot be submitted yet.', event)">
  Submit
</button>
```

```js
methods: {
  warn(message, event) {
    // 这里可以访问 DOM 原生事件
    if (event) {
      event.preventDefault()
    }
    alert(message)
  }
}
```

#### 事件修饰符

- `.stop`
- `.prevent`
- `.self`

```html
<!-- 单击事件将停止传递 -->
<a @click.stop="doThis"></a>

<!-- 提交事件将不再重新加载页面 -->
<form @submit.prevent="onSubmit"></form>

<!-- 修饰语可以使用链式书写 -->
<a @click.stop.prevent="doThat"></a>

<!-- 也可以只有修饰符 -->
<form @submit.prevent></form>

<!-- 仅当 event.target 是元素本身时才会触发事件处理器 -->
<!-- 例如：事件处理器不来自子元素 -->
<div @click.self="doThat">...</div>
```

- `.capture`
- `.once`
- `.passive`

```html
<!-- 添加事件监听器时，使用 `capture` 捕获模式 -->
<!-- 例如：指向内部元素的事件，在被内部元素处理前，先被外部处理 -->
<div @click.capture="doThis">...</div>

<!-- 点击事件最多被触发一次 -->
<a @click.once="doThis"></a>

<!-- 滚动事件的默认行为 (scrolling) 将立即发生而非等待 `onScroll` 完成 -->
<!-- 以防其中包含 `event.preventDefault()` -->
<div @scroll.passive="onScroll">...</div>
```
