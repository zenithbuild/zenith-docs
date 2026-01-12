---
title: "State"
order: 1
---

# State: The Living Breath of Apps

A variable declared, a value assigned,
In Zenith’s embrace, they’re quickly refined.
The `state` is the spark, the reactive command,
That changes the world with a flip of the hand.

No setter required, no complex decree,
Just change the value, and the UI is free.

---

## ⚡ The `state` Keyword

In Zenith, reactivity is a first-class citizen. By using the `state` keyword, you tell the compiler to track a variable and update the DOM whenever its value changes.

### Basic State

```html
<script setup="ts">
  state count = 0
  
  function increment() {
    count++ // The UI updates automatically
  }
</script>

<button onclick="increment">Count is {count}</button>
```

## 🌊 Deep Reactivity

Zenith doesn't just watch the top-level variable. It deeply tracks objects and arrays, so you can update nested properties or push to arrays without losing reactivity.

```javascript
state user = {
  name: "Judah",
  profile: {
    theme: "dark"
  }
}

// All of these updates are reactive:
user.name = "Sullivan"
user.profile.theme = "light"
```

### Arrays

```javascript
state items = ["Apple", "Banana"]

function addItem() {
  items.push("Cherry") // Reactive!
}
```

## 🛠 Atomic Updates

Zenith's runtime is optimized for "atomic" updates. When a state variable changes, Zenith only updates the specific parts of the DOM that depend on that variable. This avoids expensive virtual DOM diffing and keeps your application blazing fast.

---

## 🌌 Deep Dive: Proxying

Under the hood, Zenith uses modern JavaScript Proxies to intercept changes to your state. When the compiler sees the `state` keyword, it wraps the initialization in a reactive proxy. This allows for the "magic" of direct assignment while maintaining full control over the update cycle.

**Next Step**: [Lifecycle Hooks](../reactivity/hooks.md)
