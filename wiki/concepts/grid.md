---
concept: grid
entity_type: concept
aliases: []
sources: ["raw\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-23T04:13:26Z
---

## Definition
Grid is a CSS layout module that allows web designers and developers to create two-dimensional layouts efficiently. It extends the flexibility of layout design by providing control over the placement and size of elements using rows and columns, which are defined within a grid container. Grid builds on the foundational grid systems traditionally used in print design and wikilink-elastic-box-layout (Flexbox), which predominantly handled one-dimensional layouts, to offer more intricate and responsive designs.

## How it works
The CSS Grid Layout specification, first introduced in 2011, operates on a grid container and its grid items. For a layout to utilize Grid, the container must be explicitly identified using the `display: grid;` or `display: inline-grid;` property. Inside this container, you can define the grid layout with the `grid-template-columns` and `grid-template-rows` properties to specify the size and position of columns and rows. Each element within the container can then be placed into grid cells based on the predefined grid lines, using the `grid-column` and `grid-row` properties.

Grid automatically generates named or numbered lines or areas for columns and rows, allowing for a flexible and responsive design that adapts to layout changes. Grid items can span multiple lines or areas, providing greater control over the layout without sacrificing flexibility. For example, an item can span two rows using `grid-row: 1 / 3;` and three columns using `grid-column: 1 / 4;`. Additionally, the `grid-gap` property (now deprecated in favor of `grid-column-gap` and `grid-row-gap` or `gap`) is used to set the space between the grid lines, enhancing the usability of grid layouts.

Relative and fractional values allow Grid to effectively handle dynamic content and resize responsively, depending on the browser window size or screen resolution. The `auto` keyword, when used within column or row declarations, ensures an automatic sizing of grid tracks based on content, maintaining adaptability without necessitating explicit size definitions. Autoplacing items can be achieved by specifying the `grid-auto-flow` property, which decides the default positioning of grid items that haven't been explicitly placed into a row and column.

## Variants
The CSS Grid comes with several predefined properties and values that enhance its functionality, allowing for efficient and flexible layout design based on specific needs. Notable variants include:

- **Grid Areas:** By declaring named grid areas within the `grid-template-areas` property, designers and developers can create more intuitive and readable grid layouts. Named areas can be referenced in grid items by line number or name, providing a simpler way to position elements.
- **Grid Template Rows/Columns:** Through the `grid-template-rows` and `grid-template-columns` properties, the designer can directly control the size of rows and columns, allowing for static, fixed, or content-based sizes.
- **Grid Auto-Flow:** This property controls the direction as well as the filling of the grid. Values like `row` and `column` determine which direction the new grid items will start filling, and `dense` helps in filling gaps more efficiently.

## Trade-offs
While CSS Grid offers significant flexibility and power, it does come with certain limitations and considerations:

- **Browser Support:** Grid Layout is supported in all modern browsers and enjoys decent support across the board. However, understanding and using prefix properties (like `-ms-grid-row`, `-ms-grid-column`) might be necessary for full compatibility in older environments.
- **Learning Curve:** While grid simplifies many complex layout processes, its full realization requires a considerable understanding and familiarity with its properties and behaviors. This could constitute a learning curve for developers and designers not accustomed to CSS Grid layouts.
- **Grid vs. Flexbox:** In a one-dimensional layout scenario, Flexbox is often more straightforward and easier to implement. Developers must evaluate the nature of their layout before choosing an appropriate layout mechanism.