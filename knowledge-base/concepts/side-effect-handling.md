---
concept: side-effect-handling
entity_type: technique
aliases: ["副作用处理"]
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:34:51Z
---

## Definition
Side Effect Handling refers to the process or mechanism by which a software-design-pattern manages unintended or additional changes beyond the main effect of a function or program. More specifically, in the context of web development frameworks like [[react]], side effect handling involves dealing with tasks that produce observable changes outside the function’s output, such as HTTP requests, subscriptions to event sources, or data fetching. This concept builds on the core principles of functional programming by ensuring that functions are as pure as possible by isolating and managing their side effects.

## How it works
In a framework like React, side effects are typically handled using lifecycle methods, but these are being replaced with the use of hooks. The main Hook used for this purpose is `useEffect`. `useEffect` allows a fragment of code to run either after the component re-renders or after a certain dependency has changed.

The general syntax for `useEffect` is as follows:
```javascript
import { useState, useEffect } from 'react';

function ExampleComponent(props) {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
In this example, every time `count` updates, the component re-renders, and as a result, the `useEffect` callback is triggered, updating the document title.

`useEffect` can also have a return value that implements cleanup functionalities. This is particularly useful for subscriptions or event listeners, as acquiring a subscription might have side effects, but so does removing it. This way, `useEffect` is not only responsible for side effect handling but also for setting up and tearing down these effects in a controlled manner.

Additionally, the `useEffect` hook, and other side effect handlers in React and other frameworks, borrow principles from functional programming like currying and higher-order functions. They are designed to be modular and reusable, aligning with the functional-programming-patterns of immutable values and pure functions.

## Variants
Side effect handling varies across different frontend frameworks and architectures. In Angular, side effects are often encapsulated within the `ngAfterViewInit` or `ngOnDestroy` lifecycle hooks. Vue.js, similar to React, employs custom hooks through its `onMounted` or `onUnmounted` lifecycle hooks. Another approach is the use of observer patterns or middleware within state management libraries, such as Redux, to manage side effects outside the normal component hierarchy. Each of these systems is designed to deal with side effects without compromising the purity of the application logic, often implements the side-effect-free-functions concept by designing isolated functions or contexts that deal exclusively with side effects.

## Trade-offs
The trade-off in side effect handling involves maintaining code purity and simplicity versus the complexity and overhead introduced by isolating side effects. While the concept of isolating side effects helps in building more predictable and testable applications, it can introduce additional complexity, especially when dealing with multiple dependencies or recursive dependencies. Developers must carefully manage these dependencies to avoid performance issues or infinite loops.

Moreover, managing side effects can require developers to follow thorough documentation and best practices to ensure that side effects do not introduce unintended bugs or performance issues. This can be a steep learning curve for new developers. However, abiding by best practices depends on understanding concepts like dependency arrays in React’s `useEffect` or similar mechanisms in other frameworks, ensuring side effects are cleanly managed and optimized for performance.