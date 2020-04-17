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


## 函数输出

```js
const add = x => x + x;

function myFunc(num = 2, value = add(num)) {
  console.log(num, value);
}

myFunc();
myFunc(3);
```

- A: 2 4 and 3 6
- B: 2 NaN and 3 NaN
- C: 2 Error and 3 6
- D: 2 4 and 3 Error

<detail>
<summary>
<strong>Answer</strong>  
</summary> 
<p>太简单了点</p>
</detail>