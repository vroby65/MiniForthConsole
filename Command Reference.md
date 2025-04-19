# 📘 Command Reference

This page lists all commands supported by **Mini Forth Console**, along with descriptions and examples.

---

## 📌 Stack Manipulation

| Command | Description | Example |
|--------|-------------|---------|
| `dup` | Duplicate the top of the stack | `5 dup . . → 5 5` |
| `drop` | Remove the top element | `10 drop .$ → [empty stack]` |
| `swap` | Swap the top two elements | `1 2 swap . . → 1 2` |
| `over` | Copy the second element to the top | `1 2 over . . . → 1 2 1` |
| `clearstack` | Clears the entire stack | `1 2 3 clearstack .$ → [empty stack]` |
| `.$` | Displays the current stack | `1 2 "hi" .$ → [2: "hi"] [1: 2] [0: 1]` |

---

## ➕ Arithmetic

| Command | Description | Example |
|--------|-------------|---------|
| `+` | Add top two numbers | `3 4 + . → 7` |
| `-` | Subtract | `10 3 - . → 7` |
| `*` | Multiply | `6 7 * . → 42` |
| `/` | Divide | `12 4 / . → 3` |

---

## 🔍 Comparison

| Command | Description | Example |
|--------|-------------|---------|
| `=` | Equal | `5 5 = . → 1` |
| `!=` / `<>` | Not equal | `3 4 != . → 1` |
| `<` | Less than | `2 3 < . → 1` |
| `>` | Greater than | `3 2 > . → 1` |
| `<=` | Less than or equal | `2 2 <= . → 1` |
| `>=` | Greater than or equal | `3 2 >= . → 1` |

---

## 🔁 Loops

| Command | Description | Example |
|--------|-------------|---------|
| `do ... loop` | Loop from `start` to `end` (exclusive) | `0 5 do i . loop → 0 1 2 3 4` |
| `for ... next` | Loop `n` times | `3 for i . next → 0 1 2` |
| `i` | Push current loop index | *(used inside loops)* |
| `leave` | Exit a loop early | *(used inside loops)* |

---

## 🧠 Conditionals

| Command | Description | Example |
|--------|-------------|---------|
| `if ... else ... then` | Conditional branching | `5 3 > if "greater" else "smaller" then . → greater` |

---

## 🗃️ Variables

| Command | Description | Example |
|--------|-------------|---------|
| `variable` | Create a variable | `variable x` |
| `!` | Store into variable or array | `42 x !` |
| `@` | Fetch from variable or array | `x @ . → 42` |
| `array` | Define an empty array | `array a` |
| `*!` | Store full stack into array | `1 2 3 a *!` |
| `*@` | Push array elements to stack | `a *@ .$ → [2: 3] [1: 2] [0: 1]` |
| `.v` | List all variables and arrays | `.v → [x : 42] [a : [1, 2, 3]]` |

---

## ✍️ Words & Aliases

| Command | Description | Example |
|--------|-------------|---------|
| `: name ... ;` | Define a new word | `: square dup * ;` |
| `alias new existing` | Create an alias | `alias sqr square` |
| `see word` | Show definition | `see square → : square dup * ;` |
| `edit word` | Load definition to edit | `edit square` |
| `forget name` | Remove a word or variable | `forget square` |
| `words` | List all available words | `words` |

---

## 🧪 JavaScript

| Command | Description | Example |
|--------|-------------|---------|
| `"code" js` | Execute JS code in browser | `"alert('Hello')" js` |

> JS strings must be quoted. You can inspect variables or run calculations, e.g.:
>
> ```forth
> "2 + 3" js . → 5
> "document.title" js .
> ```

---

## 📦 Input/Output

| Command | Description | Example |
|--------|-------------|---------|
| `.` | Pop and print top of stack | `42 . → 42` |
| `cr` | Add a newline | `cr` |
| `clr` | Clear screen | `clr` |
| `$` | Start capture: next printed value is pushed | `5 2 + $ . .$ → [0: 7]` |
| `.*` | Loop: repeat until stack is empty | `1 2 3 4 .* .` → prints 4 3 2 1 |

---

## 💾 Storage

| Command | Description |
|--------|-------------|
| `save` | Download current words and variables as a file |
| `load` | Upload a previously saved environment |
| `reset` | Clear all variables, words, and stack |

---

If you find a missing feature or bug, feel free to open an issue or contribute to the project!

Happy Forth-ing 🚀

