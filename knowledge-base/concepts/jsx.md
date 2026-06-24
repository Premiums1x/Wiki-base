---
concept: jsx
entity_type: technique
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:34:09Z
---

## Definition
JSX is a syntax extension to JavaScript by React, which allows developers to write HTML-like structures directly within JavaScript code. It is not standard JavaScript but enhances the language with a more HTML-like syntax. JSX is instrumental in the development of user interfaces (UI) declarative-rendering, [[hooks]].

## How it Works
JSX extends JavaScript capabilities, essentially functioning as a lightweight template language that compiles down to JavaScript. When JSX is used in a React component, the React compiler takes the JSX code and converts it into plain JavaScript functions that create React elements. These elements are then used to render the actual DOM nodes. For example, the JSX snippet `<div>Hello World</div>` translates into JavaScript that creates a `div` element with the text `'Hello World'`.

JSX can also embed JavaScript expressions, allowing for dynamic content within components. This is achieved by wrapping expressions in curly braces `{expression}`. This feature is particularly powerful because it enables developers to interweave static HTML-like structures with dynamic JavaScript logic smoothly. For instance, the JSX `<div>{name}</div>` translates to JavaScript code that will render a `div` element containing the value of `name`.

## Variants
Several variants or implementations of JSX-like syntax exist across different frameworks. For example, Preact is a library that heavily builds on React's declarative rendering with a similar ecosystem but offers a smaller footprint. Another notable example is Vue.js, which implements a similar template syntax with components but is distinct in its reactive data binding and lifecycle management vue. Additionally, AngularJS (now Angular) has its own templating system that integrates HTML with components, angular-components which, although different in implementation and syntax, serves a comparable purpose to JSX in terms of embedding dynamic JavaScript content into HTML-like structures.

## Trade-offs
While JSX significantly simplifies the creation of dynamic DOM structures in React apps, there are several trade-offs to consider:

- **Learning Curve**: Integrating JSX with React requires developers to adapt to this augmented JavaScript syntax. This can be a barrier for developers unfamiliar with both JavaScript and templating systems in web development.

- **Toolchain Complexity**: JSX must be transpiled into regular JavaScript code before it can be used by the browser. This step of compiling JSX hurdles slightly increases the complexity of build processes, which is purely a prerequisite of integrating React into a project.

- **Runtime Performance**: Additional layers of abstraction introduced by JSX, such as the need for compiling and the overhead of virtual DOM manipulation [[virtual-dom]], can lead to a slight performance decrement compared to hand-written DOM manipulations.