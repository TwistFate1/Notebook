# CSS

## CSS 选择器

> CSS 选择器是用于选择页面上的 HTML 元素以便对其应用样式的工具。

1. 基本选择器

    - 元素选择器

    > 通过 HTML 元素的`标签名`来选择元素。

    ```html
    <p>这是一个段落。</p>
    ```

    ```css
    p {
        color: red; /* 将所有段落文本设置为红色 */
    }
    ```

    - 类选择器

    > 通过 HTML 元素的 `class` 属性来选择元素。

    ```html
    <div class="box">这是一个盒子。</div>
    ```

    ```css
    .box {
        background-color: blue; /* 将所有class为box的元素背景设置为蓝色 */
    }
    ```

    - ID 选择器

    > 通过 HTML 元素的 `id` 属性来选择元素。

    ```html
    <div id="main">这是主要内容。</div>
    ```

    ```css
    #main {
        font-size: 20px; /* 将id为main的元素字体大小设置为20像素 */
    }
    ```

    - 通用选择器

    > 选择页面上的所有元素。

    ```css
    * {
        margin: 0;
        padding: 0; /* 将所有元素的外边距和内边距设置为0 */
    }
    ```

2. 组合选择器

    - 并列选择器

    > 通过逗号分隔多个选择器，对多个选择器同时应用相同的样式。

    ```css
    h1, h2, h3 {
        color: green; /* 将h1、h2、h3的文本颜色设置为绿色 */
    }
    ```

    - 后代选择器

    > 选择某个元素内部的所有后代元素。

    ```html
    <div>
        <p>这是一个段落。</p>
    </div>
    ```

    ```css
    div p {
        color: purple; /* 选择div内部的所有p元素，将其文本颜色设置为紫色 */
    }
    ```

    - 子代选择器

    > 选择某个元素的直接子元素。

    ```html
    <div>
        <p>直接子元素段落。</p>
        <div>
            <p>间接子元素段落。</p>
        </div>
    </div>
    ```

    ```css
    div > p {
        color: orange; /* 只选择div的直接子元素p，将其文本颜色设置为橙色 */
    }
    ```

    - 相邻兄弟选择器

    > 选择某个元素的紧邻下一个兄弟元素。

    ```html
    <h1>标题</h1>
    <p>段落1</p>
    <p>段落2</p>
    ```

    ```css
    h1 + p {
        color: pink; /* 选择h1紧邻的下一个兄弟元素p，将其文本颜色设置为粉色 */
    }
    ```

3. 伪类选择器

    - 链接伪类

    > 用于对链接的不同状态进行样式设置。

    ```css
    a:link {
        color: blue; /* 未访问的链接颜色为蓝色 */
    }
    a:visited {
        color: purple; /* 已访问的链接颜色为紫色 */
    }
    a:hover {
        color: red; /* 鼠标悬停时链接颜色为红色 */
    }
    a:active {
        color: green; /* 鼠标点击时链接颜色为绿色 */
    }
    ```

    - 动态伪类

    > 用于根据元素的状态或行为选择元素。

    ```html
    <input type="text" />
    ```

    ```css
    input:focus {
        border: 2px solid green; /* 输入框获得焦点时，边框变为绿色 */
    }
    ```

    - 结构伪类

    > 根据元素在文档结构中的位置选择元素。

    ```html
    <div>
        <p>第一个段落</p>
        <p>第二个段落</p>
        <p>第三个段落</p>
    </div>
    ```

    ```css
    p:first-child {
        color: red; /* 选择div的第一个子元素p，将其文本颜色设置为红色 */
    }
    p:nth-child(2) {
        color: green; /* 选择div的第二个子元素，无论其类型，将其文本颜色设置为绿色 */
    }
    p:nth-of-type(3) {
        color: blue; /* 选择div的第三个p元素，将其文本颜色设置为蓝色 */
    }
    ```

    - 语言伪类

    > 根据元素的 `lang` 属性选择元素。

    ```html
    <p lang="en">This is English.</p>
    <p lang="zh">这是中文。</p>
    ```

    ```css
    p[lang="en"] {
        color: red; /* 选择lang为en的段落，将其文本颜色设置为红色 */
    }
    ```

4. 伪元素选择器

    > 用于选择元素的特定部分，而不是整个元素。

    ```html
    <p>这是一个段落。</p>
    ```

    ```css
    p::before {
        content: "【"; /* 在段落内容之前插入内容 */
        color: red;
    }
    p::after {
        content: "】"; /* 在段落内容之后插入内容 */
        color: red;
    }
    p::first-letter {
        font-size: 24px; /* 将段落的第一个字母字体大小设置为24像素 */
        color: blue;
    }
    ```

5. 属性选择器

    > 通过元素的属性及属性值来选择元素。
