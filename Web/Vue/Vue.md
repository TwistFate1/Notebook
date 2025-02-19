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

#### 按键修饰符

```html
<!-- 仅在 `key` 为 `Enter` 时调用 `submit` -->
<input @keyup.enter="submit" />
```

> 可以直接使用按键名称作为修饰符，但需要转为 kebab-case 形式。

```html
<input @keyup.page-down="onPageDown" />
```

> 对应 `PageDown` 调用事件处理。

- `.enter`
- `.tab`
- `.delete`
- `.esc`
- `.space`
- `.up`
- `.down`
- `.left`
- `.right`
- `.ctrl`
- `.alt`
- `.shift`
- `.meta`

> `.exact` 修饰符允许精确控制触发事件所需的系统修饰符的组合。

```html
<!-- 当按下 Ctrl 时，即使同时按下 Alt 或 Shift 也会触发 -->
<button @click.ctrl="onClick">A</button>

<!-- 仅当按下 Ctrl 且未按任何其他键时才会触发 -->
<button @click.ctrl.exact="onCtrlClick">A</button>

<!-- 仅当没有按下任何系统按键时触发 -->
<button @click.exact="onClick">A</button>
```

#### 鼠标按键修饰符

- `.left`
- `.right`
- `.middle`

### 表单输入绑定

> 手动连接值绑定和更改事件监听器：

```html
<input
  :value="text"
  @input="event => text = event.target.value">
```

> `v-model` 简化：

```html
<input v-model="text">
```

**注意：** 对于 `IME` 拼字阶段不会实时更新，如需要请手动编写！

#### 值绑定

> 利用 `v-bind` 绑定动态数据。

#### 修饰符

- `.lazy`

  ```html
  <!-- 在 "change" 事件后同步更新而不是 "input" -->
  <input v-model.lazy="msg" />
  ```

- `.number`

  ```html
  <input v-model.number="age" />
  ```

- `.trim`

  ```html
  <input v-model.trim="msg" />
  ```

### 生命周期

![lifecycle](./images/lifecycle.png "lifecycle")

### 侦听器

> `watch` 选项，在每次响应式属性发生变化时触发一个函数。

```js
export default {
  data() {
    return {
      question: '',
      answer: 'Questions usually contain a question mark. ;-)',
      loading: false
    }
  },
  watch: {
    // 每当 question 改变时，这个函数就会执行
    question(newQuestion, oldQuestion) {
      if (newQuestion.includes('?')) {
        this.getAnswer()
      }
    }
  },
  methods: {
    async getAnswer() {
      this.loading = true
      this.answer = 'Thinking...'
      try {
        const res = await fetch('https://yesno.wtf/api')
        this.answer = (await res.json()).answer
      } catch (error) {
        this.answer = 'Error! Could not reach the API. ' + error
      } finally {
        this.loading = false
      }
    }
  }
}
```

```html
<p>
  Ask a yes/no question:
  <input v-model="question" :disabled="loading" />
</p>
<p>{{ answer }}</p>
```

> `watch` 选项也支持把键设置成用 `.` 分隔的路径：

```js
export default {
  watch: {
    // 注意：只能是简单的路径，不支持表达式。
    'some.nested.key'(newValue) {
      // ...
    }
  }
}
```

#### 深层侦听器

> 深层侦听器：

```js
export default {
  watch: {
    someObject: {
      handler(newValue, oldValue) {
        // 注意：在嵌套的变更中，
        // 只要没有替换对象本身，
        // 那么这里的 `newValue` 和 `oldValue` 相同
      },
      deep: true
    }
  }
}
```

#### 及时回调的侦听器

> 强制回调函数立即执行：

```js
export default {
  // ...
  watch: {
    question: {
      handler(newQuestion) {
        // 在组件实例创建时会立即调用
      },
      // 强制立即执行回调
      immediate: true
    }
  }
  // ...
}
```

#### 一次性侦听器

```js
export default {
  watch: {
    source: {
      handler(newValue, oldValue) {
        // 当 `source` 变化时，仅触发一次
      },
      once: true
    }
  }
}
```

#### 回调的触发时机

> 默认情况下，侦听器回调会在父组件更新 (如有) 之后、所属组件的 DOM 更新之前被调用。
>
> 在侦听器回调中能访问被 Vue 更新之后的所属组件的 DOM:

```js
export default {
  // ...
  watch: {
    key: {
      handler() {},
      flush: 'post'
    }
  }
}
```

> 在 Vue 进行任何更新之前触发：

```js
export default {
  // ...
  watch: {
    key: {
      handler() {},
      flush: 'sync'
    }
  }
}
```

> 也可以使用组件实例的 `$watch()` 方法来命令式地创建一个侦听器：

```js
export default {
  created() {
    this.$watch('question', (newQuestion) => {
      // ...
    })
  }
}
```

#### 停止侦听器

> 用 `watch` 选项或者 `$watch()` 实例方法声明的侦听器，会在宿主组件卸载时自动停止。
>
> 在组件卸载之前就停止一个侦听器，这时可以调用 `$watch()` API 返回的函数：

```js
const unwatch = this.$watch('foo', callback)

// ...当该侦听器不再需要时
unwatch()
```

### 模板引用

> 直接访问底层 DOM 元素，使用特殊的 `ref`：

```html
<input ref="input">
```

#### 访问模板引用

> **挂载结束后**引用都会被暴露在 this.$refs 之上：

```html
<script>
export default {
  mounted() {
    this.$refs.input.focus()
  }
}
</script>

<template>
  <input ref="input" />
</template>
```

#### 函数模板引用

```html
<input :ref="(el) => { /* 将 el 赋值给一个数据属性或 ref 变量 */ }">
```

### 组件基础

> 组件允许我们将 UI 划分为独立的、可重用的部分，并且可以对每个部分进行单独的思考。

#### 定义一个组件

> Vue 组件定义在一个单独的 `.vue` 文件中，单文件组件（SFC）：

```html
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <button @click="count++">You clicked me {{ count }} times.</button>
</template>
```

> 不使用构建步骤时，一个 Vue 组件以一个包含 Vue 特定选项的 JavaScript 对象来定义：

```js
export default {
  data() {
    return {
      count: 0
    }
  },
  template: `
    <button @click="count++">
      You clicked me {{ count }} times.
    </button>`
}
```

#### 使用组件

```html
<script>
import ButtonCounter from './ButtonCounter.vue'

export default {
  components: {
    ButtonCounter
  }
}
</script>

<template>
  <h1>Here is a child component!</h1>
  <ButtonCounter />
</template>
```

#### 传递 props

> 当一个值被传递给 prop 时，它将成为该组件实例上的一个属性。该属性的值可以像其他组件属性一样，在模板和组件的 `this` 上下文中访问。

```html
<!-- BlogPost.vue -->
<script>
export default {
  props: ['title']
}
</script>

<template>
  <h4>{{ title }}</h4>
</template>
```

#### 事件监听

> 父组件可以通过 v-on 或 @ 来选择性地监听子组件上抛的事件，就像监听原生 DOM 事件那样：

```html
<script>
data() {
  return {
    posts: [
      /* ... */
    ],
    postFontSize: 1
  }
}
</script>

<template>
  <div :style="{ fontSize: postFontSize + 'em' }">
    <BlogPost
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      @enlarge-text="postFontSize += 0.1"
    />
  </div>
</template>
```

> 子组件可以通过调用内置的 `$emit` 方法，通过传入事件名称来抛出一个事件：

```html
<!-- BlogPost.vue -->
<script>
export default {
  props: ['title'],
  emits: ['enlarge-text']
}
</script>

<template>
  <div class="blog-post">
    <h4>{{ title }}</h4>
    <button @click="$emit('enlarge-text')">Enlarge text</button>
  </div>
</template>
```

> 通过 `emits` 选项来声明需要抛出的事件是最佳实践。

#### 通过插槽来分配内容

> 向组件中传递内容：

```html
<template>
  <AlertBox>
    Something bad happened.
  </AlertBox>
</template>
```

> 使用 `<slot>` 作为一个占位符，父组件传递进来的内容就会渲染在这里:

```html
<!-- AlertBox.vue -->
<template>
  <div class="alert-box">
    <strong>This is an Error for Demo Purposes</strong>
    <slot />
  </div>
</template>

<style scoped>
.alert-box {
  /* ... */
}
</style>
```

#### 动态组件

```html
<template>
<!-- currentTab 改变时组件也改变 -->
  <component :is="currentTab"></component>
</template>
```

## 深入组件

### 注册

#### 全局注册

> 使用 Vue 应用实例的 `.component()` 方法，让组件在当前 Vue 应用中全局可用。

```js
import { createApp } from 'vue'

const app = createApp({})

app.component(
  // 注册的名字
  'MyComponent',
  // 组件的实现
  {
    /* ... */
  }
)
```

> 如果使用单文件组件，你可以注册被导入的 `.vue` 文件：

```js
import MyComponent from './App.vue'

app.component('MyComponent', MyComponent)
```

#### 局部注册

> 局部注册需要使用 `components` 选项：

```html
<script>
import ComponentA from './ComponentA.vue'

export default {
  components: {
    ComponentA
  }
}
</script>

<template>
  <ComponentA />
</template>
```

> 对于每个 `components` 对象里的属性，它们的 key 名就是注册的组件名，而值就是相应组件的实现。

**注意：** 局部注册的组件在后代组件中不可用。

#### 组件名格式

> PascalCase 是合法的 JavaScript 标识符。
>
> Vue 支持将模板中使用 kebab-case 的标签解析为使用 PascalCase 注册的组件。

### Props

#### Props 声明

> props 需要使用 `props` 选项来定义：

```js
export default {
  props: ['foo'],
  created() {
    // props 会暴露到 `this` 上
    console.log(this.foo)
  }
}
```

> 除了使用字符串数组来声明 props 外，还可以使用对象的形式：

```js
export default {
  props: {
    title: String,
    likes: Number
  }
}
```

> 使用 camelCase 形式（合法的 JavaScript 标识符），但通常为 kebab-case 形式（和 HTML attribute 对齐）。

#### 使用一个对象绑定多个 prop

> 使用没有参数的 `v-bind`:

```js
export default {
  data() {
    return {
      post: {
        id: 1,
        title: 'My Journey with Vue'
      }
    }
  }
}
```

```html
<template>
  <BlogPost v-bind="post" />
  <!-- 等价于 <BlogPost :id="post.id" :title="post.title" /> -->
</template>
```

#### 单向数据流

> 所有的 props 都遵循着单向绑定原则。

#### Prop 校验

```js
export default {
  props: {
    // 基础类型检查
    //（给出 `null` 和 `undefined` 值则会跳过任何类型检查）
    propA: Number,
    // 多种可能的类型
    propB: [String, Number],
    // 必传，且为 String 类型
    propC: {
      type: String,
      required: true
    },
    // 必传但可为 null 的字符串
    propD: {
      type: [String, null],
      required: true
    },
    // Number 类型的默认值
    propE: {
      type: Number,
      default: 100
    },
    // 对象类型的默认值
    propF: {
      type: Object,
      // 对象或者数组应当用工厂函数返回。
      // 工厂函数会收到组件所接收的原始 props
      // 作为参数
      default(rawProps) {
        return { message: 'hello' }
      }
    },
    // 自定义类型校验函数
    // 在 3.4+ 中完整的 props 作为第二个参数传入
    propG: {
      validator(value, props) {
        // The value must match one of these strings
        return ['success', 'warning', 'danger'].includes(value)
      }
    },
    // 函数类型的默认值
    propH: {
      type: Function,
      // 不像对象或数组的默认，这不是一个
      // 工厂函数。这会是一个用来作为默认值的函数
      default() {
        return 'Default function'
      }
    }
  }
}
```

#### Boolean 类型转换

```js
// disabled 将被转换为 true
export default {
  props: {
    disabled: [Boolean, Number]
  }
}

// disabled 将被转换为 true
export default {
  props: {
    disabled: [Boolean, String]
  }
}

// disabled 将被转换为 true
export default {
  props: {
    disabled: [Number, Boolean]
  }
}

// disabled 将被解析为空字符串 (disabled="")
export default {
  props: {
    disabled: [String, Boolean]
  }
}
```

### 组件事件
