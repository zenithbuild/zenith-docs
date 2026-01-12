---
title: "Expressions"
order: 1
---

# Expressions: The Pulse of the Template

Within the braces, logic finds its breath,
Escaping static bounds and avoiding death.
A state, a math, a ternary of light,
To make the template shine and burn so bright.

The `{}` marks the spot where data flows,
As Zenith watches, and the logic grows.

---

## ⚡ The Power of `{}`

In Zenith, curly braces `{}` are more than just placeholders; they are the bridge between your JavaScript logic and your HTML structure.

### Basic Interpolation

Any valid JavaScript expression can be placed inside the braces. Zenith will evaluate it and render the result as text.

```html
<script setup="ts">
  state user = "Judah"
  state count = 5
</script>

<div>
  <p>Welcome, {user}!</p>
  <p>You have {count * 2} notifications.</p>
</div>
```

## 🛠 Complex Expressions

You aren't limited to simple variables. You can use ternaries, function calls, and template literals.

```html
<p>Status: {isLoading ? 'Searching...' : 'Ready'}</p>
<p>Time: {new Date().toLocaleTimeString()}</p>
<p>Class: {isActive ? 'text-blue-500' : 'text-gray-400'}</p>
```

## 🔄 Lists and Maps

As seen in previous chapters, `.map()` is the standard way to handle arrays. But you can do more:

```html
<ul>
  {items
    .filter(i => i.visible)
    .map(i => (
      <li class={i.priority > 5 ? 'font-bold' : ''}>
        {i.text.toUpperCase()}
      </li>
    ))
  }
</ul>
```

---

## 🌌 Deep Dive: Sanitization

Zenith's expressions are automatically sanitized to prevent XSS attacks. If you need to render raw HTML (for example, from a markdown collection), you should use a dedicated content helper or trust your source.

**Next Step**: [Templates & Layouts](../syntax/templates.md)
