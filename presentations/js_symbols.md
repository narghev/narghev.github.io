---
marp: true
theme: uncover
class: invert
---

<style>
:root {
  --red: #e53935;
  --blue: #1E88E5;
  --yellow: #f7df1e;
  --purple: #EA80FC;
}
</style>
<style scoped>
  p {
    text-align: right;
    font-size: 20px;
    margin-top: 100px;
  }
</style>

# ![width:60](./pictures/js_symbols/js_logo.png) Symbols

```js
Object.prototype[Symbol.iterator] = function* () {
  for (key of Object.keys(this)) yield [key, this[key]];
};
```

---

<style scoped>
  li {
    font-size: 35px;
  }
  p {
    display: flex;
    align-items: center;
    justify-content: space-around;
  }
</style>

![bg left:40% 80%](./pictures/js_symbols/me.jpeg)

<div>
  <span style="color: var(--red)">narghev</span>
  <span style="color: var(--blue)">:~$ </span>
  <span style="color: white">whoami</span>
</div>

```js
{
  fullName: "Narek Ghevandiani",
  company: "Hearme.app",
  technologies: [
    "Node.js",
    "React-Native",
    "GraphQL",
    "TypeScript"
  ],
  username: "narghev"
}
```

[![width:50px](./pictures/global/twitter.png)](https://twitter.com/narghev) [![width:40px](./pictures/global/linkedin.png)](https://www.linkedin.com/in/narghev/) [![width:40px](./pictures/global/github.png)](https://github.com/narghev) [![width:40px](./pictures/global/medium.png)](https://medium.com/@narghev)

---

<style scoped>
  li {
    font-size: 30px;
    list-style: none;
  }
  li::before {
    content: "•";
    color: orange;
    display: inline-block;
    width: 1em;
    margin-left: -1em
  }
</style>

# **Talk Coverage**

- What exactly is a <span style="color: var(--yellow)">JavaScript</span> Symbol
- The motivation of adding the data type to the language
- Whether the data type was successful in solving the problem it was supposed to
- The differences with the symbol data type in other languages, for example <span style="color: var(--red)">Ruby</span>
- Well-known JavaScript symbols
- Benefiting from the data type

---

### ![width:40](./pictures/js_symbols/js_logo.png) Symbol

- Added in 2015 with <span style="color: var(--blue)">**ES6**</span>
- for acting as a unique identifier of object properties
  - <span style="font-size: 25px;">**_Imagine_** _Big random numbers (uuid) as keys of an object_</span>

---

### ![width:40](./pictures/js_symbols/js_logo.png) Symbol

![width:750](./pictures/js_symbols/creating.png)

---

### ![width:40](./pictures/js_symbols/js_logo.png) Symbol

Note: <span style="color: var(--blue)">Symbol</span> is <span style="color: var(--red)">**NOT**</span> a constructor and <span style="color: var(--red)">**CANNOT**</span> be called with new

## ![width:1000](./pictures/js_symbols/constructor_error.png)

---

### ![width:40](./pictures/js_symbols/js_logo.png) Symbol

#### Global symbol registry

![width:1100](./pictures/js_symbols/global.png)

---

### ![width:40](./pictures/js_symbols/js_logo.png) Symbol

#### Global symbol registry

![width:900](./pictures/js_symbols/global_1.png)

---

### The purpose of <span style="color: var(--blue)">Symbol</span>

- Enable private properties in <span style="color: var(--yellow)">JavaScript</span>
  - <span style="font-size: 25px;">_Before symbols: closures, proxies, and other workarounds_</span>
  - <span style="font-size: 25px;">_All of the solutions are too verbose and require a lot of code and logic to achieve their purpose_</span>

---

### Using <span style="color: var(--blue)">Symbol</span> as a key

![width:650](./pictures/js_symbols/as_property.png)

---

### Comparing <span style="color: var(--blue)">Symbol</span>s

![width:700](./pictures/js_symbols/comparison.png)

---

### Accessing <span style="color: var(--blue)">Symbol</span>s

![width:900](./pictures/js_symbols/accessing.png)

---

### Comparing Global <span style="color: var(--blue)">Symbol</span>s

![width:900](./pictures/js_symbols/comparing_global.png)

---

Okay, so <span style="color: var(--blue)">**Symbol**</span>s are cool. They help us make <span style="color: var(--red)">**unique**</span> values that can never be repeated and use them to hide properties.

<span style="font-size: 50px; color: var(--yellow)">**_But do they really solve the privacy problem?_**</span>

---

#### <span style="color: var(--yellow)">JavaScript</span> symbol does <span style="color: var(--red); font-size: 80px;">NOT</span> achieve property privacy.

```js
Object.getOwnPropertySymbols();
```

![width:1100](./pictures/js_symbols/privacy.png)

---

### **Symbol in computer programming**

> A symbol in computer programming is a primitive data type whose instances have a unique human-readable form.

---

### <span style="color: var(--red)">Ruby</span> ![width:60](./pictures/js_symbols/ruby_logo.png)&#8195;Symbols

![width:800](./pictures/js_symbols/ruby_symbols.png)

---

### <span style="color: var(--yellow)">JavaScript</span> vs <span style="color: var(--red)">Ruby</span>

- We can replicate the Ruby symbol behavior by creating a symbol in the global symbol registry.
- Ruby symbols can be used instead of strings

---

### <span style="color: var(--red)">Ruby</span> Symbol Usecases

- As property identifier
- Functions returning symbol indicating status `(:ok, :error)`
  - In <span style="color: var(--red)">Rails</span> almost all HTTP status codes are available as symbols `:ok, :internal_server_error or :not_found`.

---

# **Symbols**

To conclude, we can say that symbols are not the same and do not share the same purpose in all programming languages

<span style="font-size: 35px;">_Note: In some programming languages <span style="color: var(--purple)">**(erlang, elixir)**</span>, symbol is called an atom._</span>

---

### Well-known <span style="color: var(--yellow)">JavaScript</span> symbols

JavaScript has some built-in symbols which allow the developer to access some properties which were not exposed before the introduction of symbols to the language.

---

### `Symbol.iterator`

![width:800](./pictures/js_symbols/iterable.png)

---

### `Symbol.iterator`

> <span style="color: var(--yellow)">function\*() {}</span> is the syntax for defining a <span style="color: var(--red)">generator function</span>. A generator function returns a Generator object.

> <span style="color: var(--yellow)">yield</span> is a keyword used to <span style="color: var(--red)">pause</span> and <span style="color: var(--red)">resume</span> generator functions.

<span style="font-size: 35px;">_For async iteration there is <span style="color: var(--blue)">Symbol.asyncIterator</span> which is used by for await…of loop_</span>

---

### `Symbol.match`

![width:1000](./pictures/js_symbols/match.png)

---

### `Symbol.match`

> Honestly, I am not sure why you would want to do this. The code above is an example to demonstrate how to use the <span style="color: var(--blue)">Symbol.match</span>. It seems like a hack and it will be problematic if used like this because it changes the behavior of functions that are used a lot. I cannot think of any real use-cases for using this one.

---

# Benefiting from <span style="color: yellow;">JavaScript</span> symbols

---

### **Object Metadata**

![width:1000](./pictures/js_symbols/dictionary.png)

---

### **Object Metadata and avoiding property name collision**

![width:1000](./pictures/js_symbols/dictionary_1.png)

---

### **Iterator**

![width:700](./pictures/js_symbols/iterator.png)

---

# **Thank You!**

### _Questions?_

<span style="color: var(--blue)">@narghev</span>

<span style="font-size: 15px; color: grey;">Checkout the JS symbols article on my medium</span>

![bg left width:500](./pictures/js_symbols/twitter_qr.jpeg)
