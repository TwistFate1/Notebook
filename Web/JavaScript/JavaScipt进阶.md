# JavaScript 进阶

## 对象原型

### 原型链

### 属性遮蔽

### 设置原型

## JavaScript 中的类

### 类和构造函数

```js
class Person {
  name;

  constructor(name) {
    this.name = name;
  }

  introduceSelf() {
    console.log(`Hi! I'm ${this.name}`);
  }
}
```

### 继承

```js
class Professor extends Person {
  teaches;

  constructor(name, teaches) {
    super(name);
    this.teaches = teaches;
  }

  introduceSelf() {
    console.log(
      `My name is ${this.name}, and I will be your ${this.teaches} professor.`,
    );
  }

  grade(paper) {
    const grade = Math.floor(Math.random() * (5 - 1) + 1);
    console.log(grade);
  }
}
```

### 封装

> 以 `#` 开头。

## Web API 简介

### 什么是 API?

> 应用程序接口（API）是基于编程语言构建的结构，让开发者更容易地创建复杂的功能。它们抽象了复杂的代码，并提供一些简单的接口规则直接使用。

## 客户端存储

### 老做派：cookie

### 新流派：Web 存储和 IndexedDB

> `sessionStorage` 和 `localStorage`。第一种方法，只要浏览器开着，数据就会一直保存（关闭浏览器时数据会丢失），而第二种会一直保存数据，甚至到浏览器关闭又开启后也是这样。

## 异步 JavaScript 简介

### 同步编程

> 浏览器会等待代码的解析和工作，在上一行完成后才会执行下一行。

### 事件处理程序

> 你提供的函数（事件处理程序）将在事件发生时被调用（而不是立即被调用）。

### 回调

> 回调函数则是一个被传递到另一个函数中的会在适当的时候被调用的函数。

## 如何使用 Promise

> **Promise** 是现代 JavaScript 中异步编程的基础。它是一个由异步函数返回的对象，可以指示操作当前所处的状态。

### 使用 fetch() API

```js
const fetchPromise = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json",
);

console.log(fetchPromise);

fetchPromise.then((response) => {
  console.log(`已收到响应：${response.status}`);
});

console.log("已发送请求……");
```

### 链式使用 Promise

> 在你通过 `fetch()` API 得到一个 `Response` 对象的时候，你需要调用另一个函数来获取响应数据。在这里，我们想获得 JSON 格式的响应数据，所以我们会调用 `Response` 对象的 `json()` 方法。事实上，`json()` 也是异步的，因此我们必须连续调用两个异步函数。

```js
const fetchPromise = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json",
);

fetchPromise.then((response) => {
  const jsonPromise = response.json();
  jsonPromise.then((json) => {
    console.log(json[0].name);
  });
});
```

### 错误捕获

> 为了支持错误处理，`Promise` 对象提供了一个 `catch()` 方法。这很像 `then()`：你调用它并传入一个处理函数。然后，当异步操作成功时，传递给 `then()` 的处理函数被调用，而当异步操作失败时，传递给 `catch()` 的处理函数被调用。

```js
const fetchPromise = fetch(
  "bad-scheme://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json",
);

fetchPromise
  .then((response) => {
    if (!response.ok) {
      throw new Error(`HTTP 请求错误：${response.status}`);
    }
    return response.json();
  })
  .then((json) => {
    console.log(json[0].name);
  })
  .catch((error) => {
    console.error(`无法获取产品列表：${error}`);
  });
```

### Promise 术语

> Promise 有三种状态：

- **待定（pending）**：初始状态，既没有被兑现，也没有被拒绝。这是调用 `fetch()` 返回 Promise 时的状态，此时请求还在进行中。

- **已兑现（fulfilled）**：意味着操作成功完成。当 Promise 完成时，它的 `then()` 处理函数被调用。

- **已拒绝（rejected）**：意味着操作失败。当一个 Promise 失败时，它的 `catch()` 处理函数被调用。

### 合并使用多个 Promise

```js
const fetchPromise1 = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json",
);
const fetchPromise2 = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/not-found",
);
const fetchPromise3 = fetch(
  "https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json",
);

Promise.all([fetchPromise1, fetchPromise2, fetchPromise3])
  .then((responses) => {
    for (const response of responses) {
      console.log(`${response.url}：${response.status}`);
    }
  })
  .catch((error) => {
    console.error(`获取失败：${error}`);
  });
```

### async 和 await

> `async` 关键字为你提供了一种更简单的方法来处理基于异步 Promise 的代码。在一个函数的开头添加 `async`，就可以使其成为一个异步函数。

```js
async function myFunction() {
  // 这是一个异步函数
}
```

> 在异步函数中，你可以在调用一个返回 Promise 的函数之前使用 `await` 关键字。这使得代码在该点上等待，直到 Promise 被完成，这时 Promise 的响应被当作返回值，或者被拒绝的响应被作为错误抛出。

## 如何实现基于 Promise 的 API
