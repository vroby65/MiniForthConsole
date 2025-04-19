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
- Comparisons: `= != <> > < <= >=`
- Loops: `do ... loop`, `for ... next` (with `i`, `leave`)
- Conditionals: `if ... else ... then`
- Variables: `variable`, `@`, `!`, `*`, `*@`, `*!`
- User-defined words: `: wordname ... ;`
- Aliases: `alias newname existingword`
- Persistent variables and words (`localStorage`)
- Full reset: `reset` clears words, variables, and stack
- Stack inspection: `.$`
- Variable inspection: `.v`
- Word source inspection: `see wordname`, `edit wordname`
- Forget a name (word or variable): `forget name`
- Save/load definitions and variables: `save`, `load`
- Run raw JavaScript: `"alert('hi')" js`
- Words case insensitive
- Special command: `.*` to repeat instructions until the stack is empty
- `clr` to clear screen, `cr` for newline
- Retro terminal look (customizable)
- Fully responsive, works great on desktop and mobile

---

## 🚀 Getting Started

1. Clone or download this repository:
   ```bash
   git clone https://github.com/vroby65/MiniForthConsole.git
   ```

2. Open `index.html` in your browser.

3. Start typing commands like:

```forth
3 4 + .
```

You should see:

```
→ 7 OK
```

---

## 📚 Examples

### ➕ Arithmetic

```forth
10 2 * .       \ prints 20
15 5 / .       \ prints 3
```

### 🔀 Stack Manipulation

```forth
1 2 swap . .   \ prints 1 then 2
```

### 🧠 Variables

```forth
variable x      \ define a variable
42 x !          \ store 42 into x
x @ .           \ prints 42
```

```forth
array myarr     \ define an array
10 20 30 myarr *!  \ store stack into array
myarr *@        \ push array elements back to stack
```

### 🔀 Stack Display

```forth
1 "hello" 42
.$
```

```
→ [2: 42]
[1: "hello"]
[0: 1]
```

### 📋 Variables Display

```forth
.v
```

```
→ [x : 42]
[myarr : [10, 20, 30]]
```

### 👁️ Word Inspection

```forth
: square dup * ;
see square
```

```
→ : square dup * ;
```

### 📊 Conditionals

```forth
5 3 > if "greater" else "smaller" then .
```

### 🔄 Loops

```forth
0 5 do i . loop        \ prints 0 1 2 3 4
5 for i . next         \ prints 0 1 2 3 4
```

### ✍️ Defining Words

```forth
: square dup * ;
5 square .         \ prints 25
```

### 📌 Aliases

```forth
alias sqr square
5 sqr .            \ also prints 25
```

### 🤖 Capture Output

```forth
3 4 + $ .
.$
```

This captures output of `.` and pushes it onto the stack.

### ✴️ Repeat Until Stack Empty

```forth
1 2 3 4
.* .
```

Prints all elements until stack is empty.

---

## 🪜 Management Commands

- List all words: `words`
- View variables: `.v`
- Forget a name (word or variable): `forget name`
- Reset everything (stack, vars, words): `reset`
- Clear screen: `clr`
- Save definitions & variables to file: `save`
- Load from file: `load`

---

## 📊 JavaScript Execution

Run raw JavaScript in the browser using `"your_code" js`:

```forth
"alert('Hello from Forth!')" js
```

Other examples:

```forth
"2 + 3" js .             \ prints 5
"document.title" js .    \ prints page title
```

> ⚠️ Use with caution: `js` executes arbitrary code in browser context.

---

## 💾 Save & Load

- `save` downloads both words and variables as `forth_environment.json`
- `load` imports them from file
- Environment is also saved automatically in browser `localStorage`

---

## 🎨 UI & Style

- Modern dark-mode terminal aesthetic (customizable)
- Monospaced font, responsive layout
- Smooth behavior and easy keyboard input
- Works fully offline
- No dependencies — fully self-contained

---

## 🌐 Hosting

Perfect for GitHub Pages:

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
