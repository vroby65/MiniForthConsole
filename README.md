# MiniForthConsole
javascript forth implementation
# 🖥️ Mini Forth Console

This is a simple web-based **Forth-like stack interpreter**, written entirely in HTML and JavaScript. It works directly in the browser and supports user-defined words, variables, control flow, and basic arithmetic.

Perfect for learning the basics of stack-based programming or testing Forth-style scripts quickly!



---

## 🔧 Features

- Basic arithmetic: `+ - * /`
- Stack manipulation: `dup drop swap over`
- Comparisons: `= != > <`
- Loops: `do ... loop`, `for ... next`, support for `leave` and `i`
- Conditionals: `if ... else ... then`
- Variables: `variable`, `@`, `!`, `?`
- Define and save custom words
- Export and import definitions (`save`, `load`)
- Local storage support

---

## 🚀 Getting Started

1. Clone or download this repository:
   ```bash
   git clone https://github.com/yourusername/mini-forth-console.git
   ```

2. Open `index.html` in your browser.

3. You will see a text console labeled **Mini Forth Console**.

Start typing commands like:

```forth
3 4 + .
```

You should see:

```
→ 7
```

---

## 📚 Examples

### Arithmetic

```forth
10 2 * .       \ prints 20
15 5 / .       \ prints 3
```

### Stack manipulation

```forth
1 2 swap . .   \ prints 1 then 2
```

### Variables

```forth
variable x     \ define a variable
42 x !         \ store 42 into x
x @ .          \ prints 42
x ?            \ asks user for input to store in x
```

### Conditionals

```forth
5 3 > if "greater" else "smaller" then .
```

### Loops

```forth
0 5 do i . loop        \ prints 0 1 2 3 4
5 for i . next         \ prints 0 1 2 3 4
```

---

## ✍️ Defining Words

You can define your own words using `:` and `;`

```forth
: square dup * ;
5 square .         \ prints 25
```

Use `words` to list all available words.  
Use `forget myword` to remove a custom word.  
Use `clearwords` to erase all custom words.

---

## 💾 Save and Load

- Type `save` to download your custom word definitions as `forth_words.json`.
- Type `load` to upload a JSON file containing saved definitions.

You can also use the **browser's local storage**: custom words are saved automatically when defined.

---

## 🌐 Hosting

You can host this project on [GitHub Pages](https://pages.github.com/). Just push it to your repository and enable Pages.

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙋‍♂️ Credits

Created with ❤️ by vroby65
