---
title: "Derived State"
order: 3
---

# Derived State: The Echo of Truth

From primary sources, new values arise,
Updated in secret, right 'fore your eyes.
When 'A' is adjusted, then 'B' follows suit,
The reactive blossom, the computed fruit.

No `useMemo` needed, no manual sync,
Just write the expression, it’s faster than blink.

---

## 🪞 What is Derived State?

Derived state (or computed state) is a value that is automatically calculated based on other state variables. In Zenith, you don't need special functions for this—standard expressions in your template are naturally reactive.

### Automatic Computing

```html
<script setup="ts">
  state firstName = "Judah"
  state lastName = "Sullivan"
  
  // No special 'computed' keyword needed
  function fullName() {
    return `${firstName} ${lastName}`
  }
</script>

<div>
  <h1>User: {fullName()}</h1>
</div>
```

If `firstName` or `lastName` changes, Zenith knows it needs to re-evaluate `{fullName()}` in the template.

## 🚀 Reactive Dependencies

Zenith's compiler analyzes your expressions to determine what they depend on. This "dependency tracking" ensures that updates are surgically precise.

```html
<script setup="ts">
  state items = [10, 20, 30]
  state taxRate = 0.15
</script>

<p>Total with Tax: {items.reduce((a, b) => a + b, 0) * (1 + taxRate)}</p>
```

The paragraph above will update if *either* `items` or `taxRate` changes.

## 🛠 Manual Derived State

While template expressions are usually enough, sometimes you want a variable in your script to be derived. You can do this by defining a getter or using a reactive effect.

```html
<script setup="ts">
  state score = 10
  
  // A simple getter is a great way to derive script state
  const isHighScore = () => score > 100
</script>

<div class={isHighScore() ? 'highlight' : ''}>
  Score: {score}
</div>
```

---

## 🌌 Deep Dive: Re-evaluation Strategy

Zenith uses a "pull-based" reactivity model for expressions. Instead of re-calculating everything immediately, Zenith marks expressions as "dirty" when their dependencies change and re-evaluates them just before the next paint. This debouncing prevents unnecessary work during rapid state changes.

**Next Step**: [Deep Dive into Runtime](../deep-dive/runtime.md)
