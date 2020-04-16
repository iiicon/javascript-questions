# javascript-questions

some questions about javascript

## 1 改造对象为可迭代对象

```js
const person = {
  name: "Lydia Hallie",
  age: 21,
};
```

使得 `[...person]` 能输出 `["Lydia Hallie",21]`

- A: Nothing, object are iterable by default
- B: *[Symbol.iterator]() { for (let x in this) yield* this[x] }
- C: *[Symbol.iterator]() { yield* Object.values(this) }
- D: *[Symbol.iterator]() { for (let x in this) yield this }

<details>
<summary><b>Answer</b></summary>
<p>

#### Answer: C

```js
var person = {
  name: "Lydia Hallie",
  age: 21,
  *[Symbol.iterator]() {
    yield* Object.values(this);
  },
};
以后我每天来打击你们一遍;
```

</p>
</details>
