---
concept: css-variables
entity_type: concept
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T07:56:13Z
---

## Definition
CSS Variables, also known as Custom Properties, are a part of the CSS that allow developers to define and reuse values throughout a style sheet. This feature extends the flexibility and maintainability of CSS by enabling the definition of variable-like values that can be used across multiple CSS rules. This functionality builds on the concept of css-preprocessors, which provide similar features but require the use of separate syntax or languages.

## How it works
To define a CSS Variable, a developer sets a custom property within the `:root` selector or a parent element, using the `--` syntax to prefix the variable name. Once defined, these variables can be referenced anywhere in the CSS by using the `var()` function. For example, the following code snippet declares a primary color variable:
```css
:root {
  --primary-color: #3b82f6;
}
```
This variable can then be applied to any CSS rule as shown below:
```css
button {
  background-color: var(--primary-color);
}
```
The syntax is flexible, permitting the declaration of variables across any nested scope using the parent's selector or the `:root` selector for more global variables. Variables can also be declared with default fallback values as part of the `var()` function, ensuring a defined property and an accessible value if the variable is not fully defined.
```css
button {
  background-color: var(--primary-color, #000);
}
```
CSS Variables are not only structured within CSS3 but also closely integrated with other modern CSS features such as [[flexbox]] and css-grid, contributing to dynamic and flexible styling solutions.

## Variants
Specifically, CSS Variables are available in all modern browsers and are also supported in some form by CSS preprocessors like Sass or LESS, building on those tools to offer variable-like functionality without requiring a separate preprocessor language.

## Trade-offs
While CSS Variables offer great flexibility and ease of maintenance, they also come with trade-offs. Variables can cause performance issues if not handled properly, particularly in large-scale projects. This is because browsers must recalculate the CSS values during runtime, which can be slower than simply applying predefined styles. Additionally, the usage of variables can make the style sheet more complicated and harder to debug if not managed effectively. 

On the other hand, CSS Variables are more limited in scope compared to css-preprocessors, as the variables defined in CSS are confined to the CSS for styling purposes, and do not allow the logic or operations that preprocessors like Sass offer. This may require developers to consider when they need the more advanced features provided by preprocessors.

## See also
- [[flexbox]] and css-grid extend the functionality of CSS layout and benefit from the use of CSS Variables for dynamic and flexible styling.
- css-preprocessors provides an alternative approach to achieving similar dynamic styling capabilities, offering more advanced features but at the cost of additional complexity in setup and usage.