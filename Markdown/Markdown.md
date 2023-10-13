# Markdown 标题语法
## Markdown 标题语法
### Markdown 标题语法
Title 1
=======
Title 2
-------

# Markdown 段落语法
I really like using Markdown.

# Markdown 换行语法

# Markdown 强调语法
星号（asterisk）或下划线（underscore）

## 粗体（Bold）
I **really** like using Markdown. (best)

I __really__ like using Markdown.

## 斜体（Italic）
I *really* like using Markdown. (best)

I _really_ like using Markdown.

## 粗体（Bold）和斜体（Italic）
I ***really*** like using Markdown. (best)

I ___really___ like using Markdown.

# Markdown 引用语法

## 块引用
> I really like using Markdown.

## 多个段落的块引用
> I really like using Markdown.
> 
> I really like using Markdown.

## 嵌套块引用
> I really like using Markdown.
> 
> > I really like using Markdown.

## 带有其他元素的块引用
> #### I really like using Markdown.
> 
> - I really like using Markdown.
> 
> *I* **really** like using Markdown.

# Markdown 列表语法

## 有序列表
1. First
2. Second
3. Third
   1. Forth
   2. Fifth

## 无序列表
(best)
- First
- Second
- Third
  - Forth
  - Fifth

* First
* Second
* Third

+ First
+ Second
+ Third

## 列表中嵌套其他元素

### 段落
- First
- Second

    I really like using Markdown.

- Third

### 引用块
- First
- Second

    > I really like using Markdown.

- Third

### 代码块
1. First
2. Second

        I really like using Markdown.

3. Third

### 图片
1. First
2. Second

    ![Tux, the Linux mascot](./picture/Linux.png)

3. Third

# Markdown 代码语法

## 反引号
`code` with `OD`

## 转义反引号
``Use `code` in your Markdown file.``

## 代码块
    <html>
        <head>
        </head>
    </html>

# Markdown 分隔线语法
***
星号

---
破折号（best）

___
划线

# Markdown 链接语法
这是一个链接 [Markdown语法](https://markdown.com.cn)

## 给链接增加Title
这是一个链接 [Markdown语法](https://markdown.com.cn "最好的Markdown教程")

## 网址和Email地址
<https://markdown.com.cn>
<od_code_01@qq.com>

## 带格式化的链接
I love supporting the **[EFF](https://eff.org)**.

This is the *[Markdown Guide](https://www.markdownguide.org)*.

See the section on [`code`](#code).

## 引用类型链接

### 第一部分格式
[hobbit-hole][1]

[hobbit-hole][2]

[hobbit-hole][3]

[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle

[2]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle 'Hobbit lifestyles'

[3]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle (Hobbit lifestyles)

[link](https://www.example.com/my%20great%20page)

# Markdown 图片语法
![这是图片](./picture/Linux.png "Linux")

## 链接图片
[![这是图片](./picture/Linux.png "Linux")](https://markdown.com.cn)

# Markdown 转义字符语法
\*

&amp;

&lt;

&copy;

AT&T

4 < 5

# Markdown 内嵌HTML标签

## 行级内联标签
<em>word</em>

## 区块标签
<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

# 扩展语法

# Markdown 表格
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

## 对齐
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

## 格式化表格中的文字

## 在表中转义管道字符
&#124;

# Markdown 围栏代码块
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
~~~
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
~~~

## 语法高亮
```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

# Markdown 脚注
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

# Markdown 标题编号

## My Great Heading{#custom-id}

## 链接到标题ID
[Heading IDs](#heading-ids)

[Heading IDs](https://markdown.com.cn/extended-syntax/heading-ids.html#headid)

# Markdown 定义列表
First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.

# Markdown 删除线
~~世界是平坦的。~~ 我们现在知道世界是圆的。

# Markdown 任务列表语法
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

# Markdown 使用 Emoji 表情
emoji shortcodes

## 复制和粘贴表情符号
⛺

## 使用表情符号简码
去露营了！ :tent: 很快回来。

真好笑！ :joy:

# 自动网址链接
http://www.example.com