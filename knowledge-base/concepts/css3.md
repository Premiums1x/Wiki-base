---
concept: css3
entity_type: concept
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:34:18Z
---

## Definition

CSS3 (Cascading Style Sheets, level 3) is a style sheet language used for describing the look and formatting of a document written in HTML or XML. Building on the css2 syntax, CSS3 introduces new features and improvements that make styling web pages more powerful and expressive.

## How it works

CSS3 operates by specifying rules that define how HTML and XML elements should be rendered in a visual medium. These rules consist of selectors that target elements and declarations that set various properties such as color, padding, layout, and more. They work by cascading, meaning that if multiple styles apply to an element, CSS rules are prioritized based on specificity and the order in which they are declared.

### Modern CSS Layouts

CSS3 introduces the concept of modern layouts such as [[flexbox]] and [[grid]]. Flexbox is used to create flexible boxes that can change size based on available space and layout needs. Grid allows for two-dimensional layout by creating rows and columns, enabling more complex layouts with better control over elements positioning.

### CSS Variables

CSS3 supports custom properties known as CSS variables that web-developers can use to store and reuse values throughout stylesheets. This improves efficiency by allowing web-developers to define a variable once and use it across the document for flexibility and maintainability.

## Variants

CSS3 is the latest version of the CSS standard and is implemented by most web browsers including chrome, firefox, and edge. It extends HTML5 by introducing numerous modules and features like animations, transforms, transitions, and advanced selectors, making web design more dynamic and interactive.

## Trade-offs

While CSS3 is powerful and flexible, it also introduces complexity that can be overwhelming for beginners. Additionally, some CSS3 features may not be supported by older browsers, necessitating the use of polyfills or fallback techniques. Furthermore, reliance on CSS3 can trade-off browser performance due to complex styles and significant stylesheet sizes.

## See also

[[flexbox]], [[grid]], css2, web-developers, [[html5]]