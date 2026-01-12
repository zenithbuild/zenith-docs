---
title: "Hooks"
order: 2
---

# Hooks: The Rhythms of Life

When elements bloom and find their first light,
Or vanish like shadows in depths of the night.
The hooks are the timers, the beats of the heart,
That govern the life of your Zenith-born art.

From mount until death, in a cycle so clear,
The hooks keep the logic and purpose quite near.

---

## 🎣 Lifecycle Hooks

Zenith provides a set of intuitive hooks to tap into the lifecycle of your components.

### `zenOnMount`

Triggered when the component is first injected into the DOM. This is the perfect place for API calls or initializing third-party libraries.

```javascript
<script setup="ts">
  import { zenOnMount } from 'zenith:core'
  
  state data = null

  zenOnMount(async () => {
    const response = await fetch('/api/data')
    data = await response.json()
    console.log("Component is now alive!")
  })
</script>
```

### `zenOnUpdate`

Runs whenever the component's state or props have changed and the DOM has been updated.

```javascript
import { zenOnUpdate } from 'zenith:core'

zenOnUpdate(() => {
  console.log("The DOM has shifted its form.")
})
```

### `zenOnUnmount`

The final curtain call. Use this to clean up timers, event listeners, or subscriptions.

```javascript
import { zenOnUnmount } from 'zenith:core'

const timer = setInterval(() => { /* ... */ }, 1000)

zenOnUnmount(() => {
  clearInterval(timer)
  console.log("Component has left the stage.")
})
```

---

## 💡 Best Practices: Hook Hygiene

- **Stay Inside `setup`**: Hooks must be called within the `<script setup>` block.
- **Avoid Heavy Work in `Update`**: `zenOnUpdate` can fire frequently. Keep the logic inside it lean to maintain performance.
- **Clean Up**: Always use `zenOnUnmount` for global listeners (like `window.addEventListener`) to prevent memory leaks.

**Next Step**: [Derived State & Computed Expressions](../reactivity/derived.md)
