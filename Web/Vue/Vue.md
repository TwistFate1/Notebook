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
