# 📘 Learning Notes – Pathfinding Visualizer

This document captures key React and TypeScript concepts I learned while building the **Pathfinding Visualizer** project.

---

## 1️⃣ Why do we use `types.ts`?

### ❓ Question  
What is the use of the `types.ts` file?

### ✅ Answer  
`types.ts` is used to **centralize shared TypeScript interfaces and types** so that algorithms, components, and state management all follow a **consistent data contract**.

### 💡 Why this matters
- Avoids duplicate type definitions
- Improves maintainability as the project grows
- Ensures type safety across:
  - algorithms
  - React components
  - grid/state logic

In short, `types.ts` acts as a **single source of truth for data structures**.

---

## 2️⃣ Why use `useRef` instead of `useState` for `isVisualizationRunningRef`?

### ❓ Question  
Why does using `useRef` for `isVisualizationRunningRef` improve performance compared to `useState`, especially during frequent mouse events?

### ✅ Answer  
`useRef` improves performance because **updating a ref does not trigger a component re-render**, whereas updating state with `useState` **does trigger a re-render**.

### 💡 Practical Insight
In this project:
- Mouse events (hover, drag, click) fire **very frequently**
- Using `useState` would cause unnecessary re-renders
- `useRef` allows us to:
  - track whether visualization is running
  - read/update the value instantly
  - avoid UI performance issues

👉 **Rule of thumb**:  
Use `useRef` when you need to store mutable values **without affecting rendering**.

---

## 3️⃣ What is a re-render in React?

### ❓ Question  
What does it mean when a component re-renders?

### ✅ Answer  
When a component re-renders, React **efficiently updates only the parts of the UI that depend on changed state or props**. It does **not reload the entire application**.

### 🧠 Intuition
- Re-render ≠ page reload
- React performs a **virtual DOM diff**
- Only the changed UI elements are updated

### 📖 Analogy
- **Reloading an app**: Closing a book and opening it again from the start  
- **Re-rendering a component**: Highlighting one sentence in a digital book — only that sentence changes, the rest stays the same

### ⚠️ Performance Note
Re-renders are essential for keeping UI in sync with data, but:
- Too many unnecessary re-renders can hurt performance
- Hooks like `useRef`, memoization, and proper state design help optimize this

---

## 🧠 Key Takeaways

- Centralized types improve consistency and scalability
- `useRef` is ideal for frequently updated values that don’t affect UI
- Understanding re-renders is critical for writing performant React apps

---

📌 *This document will be continuously updated as I learn more concepts while extending the project.*
