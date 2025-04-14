# 🖥️ Mini Forth Console

A simple web-based **Forth-like stack interpreter**, built entirely with HTML and JavaScript.  
It runs in your browser, supports user-defined words, variables, control flow, stack manipulation — and even raw JavaScript execution.

Perfect for learning stack-based programming or quickly testing Forth-style logic!

## 🌐 Demo

Try it live: [https://vroby65.github.io/MiniForthConsole/](https://vroby65.github.io/MiniForthConsole/)

---

## 🔧 Features

- Arithmetic: `+ - * /`
- Stack manipulation: `dup drop swap over`
- Comparisons: `= != > <`
- Loops: `do ... loop`, `for ... next` (with `i`, `leave`)
- Conditionals: `if ... else ... then`
- Variables: `variable`, `@`, `!`, `?`
- User-defined words: `: wordname ... ;`
- Built-in word listing: `words`, `forget`, `clearwords`
- Stack inspection: `.$`
- Variable inspection: `.v`
- Word source inspection: `see wordname`
- Save/load definitions (`save`, `load`)
- Persistent storage via browser localStorage
- Run raw JavaScript: `"alert('hi')" js`
- **Retro terminal look**: green-on-black
- **Fully responsive**, works great on desktop and mobile

---

## 🚀 Getting Started

1. Clone or download this repository:
   ```bash
   git clone https://github.com/yourusername/mini-forth-console.git
   ```

2. Open `index.html` in your browser.

3. Start typing commands like:

```forth
3 4 + .
```

You should see:

```
→ 7
```

---

## 📚 Examples

### ➕ Arithmetic

```forth
10 2 * .       \ prints 20
15 5 / .       \ prints 3
```

### 🌀 Stack Manipulation

```forth
1 2 swap . .   \ prints 1 then 2
```

### 🧠 Variables

```forth
variable x     \ define a variable
42 x !         \ store 42 into x
x @ .          \ prints 42
x ?            \ prompt user to enter a value
```

### 🔁 Conditionals

```forth
5 3 > if "greater" else "smaller" then .
```

### 🔂 Loops

```forth
0 5 do i . loop        \ prints 0 1 2 3 4
5 for i . next         \ prints 0 1 2 3 4
```

### ✍️ Defining Words

```forth
: square dup * ;
5 square .         \ prints 25
```

Manage words:

- List all: `words`  
- Remove one: `forget wordname`  
- Clear all custom: `clearwords`

---

## 🔍 Inspecting State

### 📦 Stack: `.$`

Displays the current stack top-to-bottom:

```forth
1 "hello" 42
.$
```

```
→ [2: 42]
[1: "hello"]
[0: 1]
```

### 📋 Variables: `.v`

Lists all defined variables and their values:

```forth
.v
```

```
→ [x: 42]
[y: "hello"]
```

### 🔎 Word Source: `see`

Displays the source of a custom word:

```forth
see square
```

```
→ : square dup * ;
```

---

## 🧪 JavaScript Execution

Run raw JavaScript in the browser using `"your_code"` `js`:

```forth
"alert('Hello from Forth!')" js
```

Other examples:

```forth
"2 + 3" js .             \ prints 5
"document.title" js .    \ prints page title
```

> ⚠️ Be cautious: `js` executes arbitrary code in the browser context. Use in trusted environments only.

---

## 💾 Save & Load

- Type `save` to download your current words as `forth_words.json`
- Type `load` to import previously saved definitions
- Definitions are also auto-saved in local storage

---

## 🎨 UI & Style

- Green-on-black retro terminal aesthetic
- Monospaced font, large text
- Smooth, responsive layout
- No dependencies — fully self-contained

---

## 🌐 Hosting

This project is fully client-side and perfect for GitHub Pages:

1. Push to your GitHub repository  
2. Enable Pages in repo settings  
3. Share your own interactive console online!

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙇‍♂️ Credits

Created with ❤️ by **vroby65**

---

Happy Forth-ing! 🤖
