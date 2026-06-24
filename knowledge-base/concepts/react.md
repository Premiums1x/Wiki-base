---
concept: react
entity_type: concept
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:34:07Z
---

## React

### Definition
React, created by Facebook in 2013, is a JavaScript library for building user interfaces, particularly single page applications (SPAs). It provides a declarative approach to describing user interfaces, focusing on reusability and encapsulation of UI code. React extends Single Page Application (SPA) frameworks by integrating dynamic rendering and state management within its core principles, making it easier to develop large and complex applications.

### How it works
React works by allowing developers to create reusable UI components using JSX, an extension to JavaScript that enables an HTML-like syntax to embed expressions with curly braces. Components are small, isolated pieces of rendering logic that accept input (properties and state) and output HTML (or components) to the screen. They can be rendered directly in the DOM as individual components or nested in a hierarchy, enabling complex interactions and dynamic updates.

The framework is built around the concept of a virtual DOM, which is a lightweight copy of the actual DOM. React updates and renders components efficiently by first calculating and figuring out exactly what has changed by diffing the current and previous states of the virtual DOM, and then only applying the minimal necessary changes to the real DOM, enhancing performance by reducing unnecessary operations.

React also introduces the concept of state and props for managing data flow in components. State is data that lives inside a component, maintained internally, and can be updated to trigger UI re-renders. Props, on the other hand, are used to pass data from a parent component to its children.

Hooks, introduced in React 16.8, enable functional components to use state and lifecycle features without writing class components. They allow developers to encapsulate and manage side effects, state, local state, and context, within functions.

### Variants
There are several popular implementations and variants of React:

- **Next.js**: Implements React by running on the server (SSR) before sending the fully hydrated app to the client. Next.js builds on React by adding features like automatic code splitting, server rendering, and built-in support for static site generation (SSG).
- **Gatsby**: An open-source static site generator for React that optimizes performance by pre-rendering web pages for lightning-fast, budget-friendly hosting, similar to static sites. Gatsby optimizes React applications for better scalability and performance, especially for content-driven websites.
- **Create React App**: A straightforward way to set up a new React project.

### Trade-offs
React has several notable trade-offs and limitations to consider:

- React's approach to UI development is highly opinionated, which means it may be less flexible for projects that require more fine-grained control over the UI or performance-critical applications beyond what React's declarative model allows.
- The virtual DOM optimization, while effective, can add some overhead compared to directly modifying the actual DOM, especially in less complex scenarios where full re-rendering might be faster. However, the benefits in complex applications usually outweigh this overhead.
- The JSX syntax might present a steep learning curve for developers unfamiliar with this approach to structuring HTML, and requires transpiling to regular JavaScript, which can add build-time complexity.
- React's ecosystem is vast, which can cause versioning conflicts and compatibility issues with other JavaScript libraries or frameworks. Managing dependencies and ensuring compatibility can be challenging.

### See also
[[html5]] [[css3]] front-end-development [[jsx]] [[virtual-dom]]