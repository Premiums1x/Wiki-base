---
concept: react
entity_type: concept
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T07:56:26Z
---

## Definition
React is a JavaScript library for building user interfaces, particularly for single-page applications. It enables declarative programming, where you specify what the UI should look like and React takes care of efficiently updating the UI to reflect changes in the underlying data. React is widely used by developers for its improved development productivity and enhanced user experience. React wikilink extends HTML5 & CSS3 by adding the ability to create complex, interactive UIs with JavaScript.

## How it works
React works by allowing developers to write components with JavaScript that render to a virtual DOM element. Components can be used to build up complex UIs from simple, reusable pieces. React uses JSX as a syntax extension to JavaScript, enabling the direct inclusion of template-like HTML structures within JavaScript code. JSX code is compiled into standard JavaScript, which can then be efficiently managed by the React runtime.

State management in React is primarily handled through the use of hooks like `useState` and `useEffect`. `useState` allows components to maintain and update their state, while `useEffect` notifies React of side effects, such as making HTTP requests or managing subscriptions. React’s virtual DOM optimizes the rendering process by maintaining a copy of the actual DOM in memory and only updating the actual DOM when changes are necessary.

## Variants
While React is the original creation from Facebook, other libraries and frameworks have emerged that implement similar principles and integrate closely with React. Next.js wikilink, for instance, is a framework built for React that optimizes performance and simplifies server-side rendering and static generation. Meanwhile, Redux wikilink, a state management library, can be used in conjunction with React to manage larger and more complex application states in a scalable and predictable manner. React Native wikilink, another variant, builds on React's ability to manage UI component states by allowing developers to use it to build native mobile applications for Android and iOS platforms.

## Trade-offs
React introduces a moderate learning curve for new users, particularly those unfamiliar with JavaScript's ES6+ features and modern web development practices. The use of JSX can be considered nonstandard compared to pure HTML, which may hinder integration with certain static analysis tools and certain linters. Additionally, while React's virtual DOM greatly improves performance in client-side applications, it can introduce additional overhead and complexity in more server-led environments where such optimizations are less beneficial.

Furthermore, the need for state management tools such as Redux can complicate application architecture and development workflows, requiring developers to manage application state across multiple components effectively. This can lead to increased reliance on third-party libraries and more complex codebases.

## See also
- html5
- css3
- [[typescript]]
- vuejs
- javascript