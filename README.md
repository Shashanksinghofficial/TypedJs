
# 📌 JavaScript Types

### 🔹 Primitive Types (Fixed)

* `string` → `"Hello"`
* `number` → `25`, `3.14`
* `boolean` → `true`, `false`
* `null` → `null`
* `undefined` → `undefined`
* `bigint` → `1234567890n`
* `symbol` → `Symbol("id")`

👉 Value fix रहती है, memory में directly store होती है।

---

### 📦 Non-Primitive Types (Reference)

* `object` → `{ name: "Shashank", age: 20 }`
* `array` → `[1, 2, 3, 4]`
* `function` → `function greet() { alert("Hi!") }`

👉 Reference (pointer) के through memory में store होते हैं।

---

# ✨ Typed.js Documentation

## ✅ Part 1: Basic Setup

```html
<!-- Step 1: Include CDN -->
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>

<!-- Step 2: Target Element -->
<span id="typed"></span>

<!-- Step 3: Initialize -->
<script>
  var typed = new Typed("#typed", {
    strings: ["Namaste!", "Swagat hai aapka", "Foodime mein"],
    typeSpeed: 50
  });
</script>
```

**Output →**
👉 Namaste! → delete → Swagat hai aapka → delete → Foodime mein

---

## ⚙️ Part 2: Options (Most Used)

| Option           | काम (Hindi)             | Default |    |
| ---------------- | ----------------------- | ------- | -- |
| `strings`        | Typing text             | `[]`    |    |
| `typeSpeed`      | Typing speed (ms/char)  | `50`    |    |
| `backSpeed`      | Deleting speed          | `50`    |    |
| `startDelay`     | Typing से पहले delay    | `0`     |    |
| `backDelay`      | Backspace से पहले delay | `700`   |    |
| `loop`           | बार-बार repeat          | `false` |    |
| `showCursor`     | Cursor दिखाना/छुपाना    | `true`  |    |
| `cursorChar`     | Cursor symbol           | \`      | \` |
| `smartBackspace` | Sirf बदले chars delete  | `true`  |    |

---

## 🧪 Example: Hero Banner (Foodime)

```html
<span id="tagline"></span>

<script>
var typed = new Typed("#tagline", {
  strings: ["Taza. Swadisht. Ghar jaisa.", "Desi khaana. Desi swaad."],
  typeSpeed: 60,
  backSpeed: 40,
  backDelay: 1000,
  startDelay: 500,
  loop: true,
  showCursor: true,
  cursorChar: "|",
  smartBackspace: true
});
</script>
```

---

## 🎯 Part 3: Advanced Use Cases

### ✅ 1. Typing Inside Button

```html
<button>
  <span id="btn-text"></span>
</button>

<script>
var typed = new Typed("#btn-text", {
  strings: ["Order Now", "Try Now", "Grab Offer"],
  typeSpeed: 50,
  backSpeed: 30,
  loop: true
});
</script>
```

---

### ✅ 2. Delay & Custom Cursor

```javascript
var typed = new Typed("#typed", {
  strings: ["Welcome to Foodime!"],
  typeSpeed: 50,
  startDelay: 2000,   // 2 sec delay
  cursorChar: "_"
});
```

---

### ✅ 3. Dynamic Array

```javascript
let menuItems = ["Paneer Tikka", "Dal Makhani", "Aloo Paratha"];

new Typed("#typed", {
  strings: menuItems,
  loop: true,
  typeSpeed: 60,
  backSpeed: 40
});
```

---

## 🚫 Errors to Avoid

* ❌ `id` गलत लिखा → target नहीं मिलेगा
* ❌ Typed.js पहले load हो गया → error आएगा
* ❌ `<script>` body के end में नहीं लिखा → DOM ready से पहले चलेगा

---

## ✨ Extra Features

### ✅ Hide Cursor

```javascript
var typed = new Typed("#typed", {
  strings: ["Welcome!"],
  typeSpeed: 60,
  showCursor: false
});
```

**CSS Customize Cursor**

```css
.typed-cursor {
  color: red;
  animation: blink 0.8s infinite;
}
```

---

### ✅ Bold / Italic (HTML support)

```javascript
var typed = new Typed("#typed", {
  strings: ["<strong>Hello</strong>, <em>World</em>!"],
  typeSpeed: 60,
  contentType: "html"
});
```

---

### ✅ Events (Callbacks)

```javascript
var typed = new Typed("#typed", {
  strings: ["Hello!", "Typing done?"],
  typeSpeed: 50,
  onComplete: function(self) {
    alert("Typing Complete!");
  },
  onStringTyped: function(pos, self) {
    console.log("Typed string index:", pos);
  }
});
```

---

### ✅ Input Placeholder Typing

```html
<input type="text" id="typedInput" />

<script>
var typed = new Typed("#typedInput", {
  strings: ["Your Name", "Email", "Mobile Number"],
  typeSpeed: 100,
  attr: "placeholder",
  bindInputFocusEvents: true
});
</script>
```

---

### ✅ Pause & Resume

```html
<button onclick="typed.stop()">Pause</button>
<button onclick="typed.start()">Start</button>

<script>
typed.stop();   // Pause
typed.start();  // Resume
</script>
```
