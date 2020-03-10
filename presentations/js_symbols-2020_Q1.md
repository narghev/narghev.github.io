---
marp: true
theme: uncover
class: invert
---

<style scoped>
  p {
    text-align: right;
    font-size: 20px;
    margin-top: 100px;
  }
</style>

# ![width:60](./pictures/js_symbols-2020_Q1/js_logo.png) Symbols

```js
Object.prototype[Symbol.iterator] = function* () {
  for (key of Object.keys(this))
    yield [key, this[key]]
}
```

JavaScript Armenia Meetup #1

---
<style scoped>
  li {
    font-size: 35px;
  }
  p {
    display: flex;
    align-items: center;
    justify-content: space-around;
    color: #43A047;
  }
</style>

![bg left:40% 80%](./pictures/js_symbols-2020_Q1/me.jpeg)
```
narghev:~$ whoami
```
- Software Engineer @[GRÜV](https://gruv.me/)
  - Node.js, React, TypeScript
- Admin and Founder @[Iterate Hackerspace](https://www.facebook.com/groups/iterate/)

@narghev [![width:50px](./pictures/global/twitter.png)](https://twitter.com/narghev) [![width:40px](./pictures/global/linkedin.png)](https://www.linkedin.com/in/narghev/) [![width:40px](./pictures/global/github.png)](https://github.com/narghev) [![width:40px](./pictures/global/medium.png)](https://medium.com/@narghev)