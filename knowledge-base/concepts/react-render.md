---
concept: react-render
entity_type: technique
aliases: ["声明式渲染"]
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:34:40Z
---

## React Render

### Definition
React render is a process by which React converts a tree of React components specified by the developer back into a web page visible in the web-browsers. It is an integral part of React's state-of-the-art [[virtual-dom]] architecture, which enhances the efficiency of UI rendering.

### How it works
React render works via a two-step process involving the description of UI state via component-defined hierarchies and then updating the DOM to reflect any changes incurred by state updates. The rendering starts by transforming component logic into a series of nested, intermediate virtual DOM representations, known as the [[jsx]] virtual DOM tree. This tree mirrors the structure of the user interface described by the JSX output.

When the component state changes, React performs a diff algorithm to determine the minimal set of changes required to update the virtual DOM to reflect the new UI configuration. This selective computation minimizes the amount of DOM operations, leading to more efficient and faster rendering cycles compared to a full rebuild of the DOM. After identifying the necessary changes, React commits these modifications to the browser's real-dom, ensuring the web page reflects the updated component hierarchy.

The hooks-responsive-state-management specifically enhance this process by allowing the developers to add state and lifecycle behavior to function components, simplifying the react render strategy and making UI updates more predictable and efficient.

### Variants
There are several ways React render might process updates to UI:

- **Direct Updates:** In scenarios where the render function returns the exact same structure (or a structure which, after reconciliation, results in no visible change), React may directly cover the previous rendered section if it is a text node.

- **Hydration:** In server-side rendering (SSR) scenarios, React must initially render the component tree on the server and hydrate (turn into functional, interactive components) that tree on the client side. This variant of rendering is commonly observed in applications leveraging SPAs (Single Page Applications) for immediate content delivery and client-side interactive functionality.

- **Incremental Updates:** React might also choose to only partially update the UI, even in cases where a component has more than one child. This incremental update strategy aims to avoid unnecessary re-renders of unchanged parts of the UI hierarchy.

### Trade-offs
One significant trade-off of using React's render approach is its performance impact on the initial load of components, especially if the application is bootstrapping a large number of elements. While React offers subsequent rendering optimizations via its virtual DOM and diffing algorithms, the initial creation of the virtual DOM and the subsequent hydration process can introduce delays, particularly noticeable in applications with numerous nested components.

Another consideration is that the real-dom (traditional way of modifying the UI) is inherently costly in terms of performance due to its complexity and size, making React's virtual DOM and diffing strategy a more lightweight alternative for UI updates.

### See also
For more information on mechanisms that improve the efficiency of React's UI logic and data flow, refer to [[virtual-dom]] and [[jsx]].