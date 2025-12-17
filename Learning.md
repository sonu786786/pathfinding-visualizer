1 )What is the use of types.ts file ? 
Ans) types.ts is used to centralize shared TypeScript interfaces and types so that algorithms, components, and state management all follow a consistent data contract.

2) Why using a useRef hook for isVisualizationRunningRef instead of a useState hook improves performance for frequent checks, especially during mouse events.
Ans)  The reason useRef improves performance in this scenario is because refs do not cause re-renders when updated, whereas changing the value of a useState hook does trigger a re-render of the component.

3) What is re-render?
Ans) when a component re-renders, React efficiently updates only the necessary parts of the user interface that have changed. It's more like refreshing or repainting a specific section of the screen based on new data (state or props).

Think of it like this:

Reloading the application: Imagine closing a book and opening it again from the very beginning. Everything is reset.
Re-rendering a component: Imagine you're reading a digital book, and you highlight a sentence. The rest of the page stays the same, but that one sentence visually changes. React only "repaints" that highlighted sentence, not the whole page or book.
Re-renders are a core part of how React keeps your UI in sync with your data, but too many unnecessary re-renders can impact performance, which is why hooks like useRef are useful in specific situations.

4) 