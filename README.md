# Hender
A tiny, handy static site generator.

## API

### require(prefix)
A function to create a render function. `prefix` is used for the syntax style. Default is `.[`.

In frontend, The main function is called as `hender()` with same arguments.

Return `function` of `render`.

### render(string, joinStr)
A function to render a string into a HTML string. A `joinStr` is used for the joined result.

## Examples

### Basic
#### index.hr
```
.[h1 Hello World!
.[p How's everyone doing? Hope you guys are doing fine.
I had a lot of work that should be done!
```

#### index.js
```js
const render = require("hender")();
const fs = require("fs");

let rendered = render(fs.readFileSync("index.hr", "utf8"));
console.log(rendered);
```
Will result:
```
<h1>Hello World!</h1><p>How's everyone doing? Hope you guys are doing fine.<br>I had a lot of work that should be done!</p>
```

### Custom Prefix
#### index.hr
```
.<h1 Hello World!
.<p How's everyone doing? Hope you guys are doing fine.
I had a lot of work that should be done!
```

#### index.js
```js
const render = require("hender")(".<");
const fs = require("fs");

let rendered = render(fs.readFileSync("index.hr", "utf8"));
console.log(rendered);
```
Will result:
```
<h1>Hello World!</h1><p>How's everyone doing? Hope you guys are doing fine.<br>I had a lot of work that should be done!</p>
```

## Community
- [Telegram Group](https://t.me/yonlecoder)
- IRC: #yonle on libera.chat
