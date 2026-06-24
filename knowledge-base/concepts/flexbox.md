---
concept: flexbox
entity_type: technique
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T09:33:42Z
---

## Definition
Flexbox, short for Flexible Box Layout, is a layout mode in CSS designed to improve the layout of items in a container. It enables the creation of flexible and adaptable layouts that can accommodate changes in item properties (such as width, height, and order) in a more effective way compared to traditional layouts like table or grid-based methods. Flexbox provides a more powerful and efficient method for controlling layout designs, particularly useful for responsive web design scenarios. It [[grid]] as an implementation of a modern CSS layout system.

## How it works
Flexbox operates by setting the display style of a container element to `flex`, which means its child elements are now flexible items. Once an element is designated as a flex container, the items inside it are lined up and grow in a flexible way. This layout model offers a means to arrange elements in a primary axis (main axis) and a cross axis.

### Main Axis and Cross Axis
- **Main Axis**: Refers to the primary direction in which flex items are laid out (either horizontally or vertically depending on the flex direction).
- **Cross Axis**: Is the axis perpendicular to the main axis.

### Flexible Properties
- **flex-direction (flex-direction)**: Determines the direction in which flex items are placed within the container (row | row-reverse | column | column-reverse).
- **justify-content (justify-content)**: Controls how the items are aligned along the main axis. Alignment options include flex-start, flex-end, center, space-between, and space-around.
- **align-items (align-items)**: Aligns the items along the cross axis in the main flex container. Possible values include stretch, center, flex-start, and flex-end.
- **align-content**: In multi-line flex containers, this property sets the distribution of space between and around the flex lines. Applies only when the container’s `align-items` isn’t set to stretch, and there is extra room in the cross-axis.
- **flex-wrap (flex-wrap)**: Controls whether items should wrap to enable multi-line layouts (nowrap, wrap, wrap-reverse).
- **order**: Defines the order in which an item appears in the flex container, an integer value where 0 is default, positive values are sorted in ascending order, and negative values are sorted in descending order.

### Flex Items
These items can change size based on the properties defined for the flex container and the flex item. Key flex item properties include:
- **align-self**: Overrides the `align-items` property for a specific item.
- **flex-grow (flex-grow)**: Incremental value that controls how much the item will grow relative to the rest of the flexible items within the same container (default is 0).
- **flex-shrink (flex-shrink)**: Flex shrink factor, allowing items to shrink if the container space is less than what the items require (default is 1). A shrink factor of 0 means the item will not shrink.

## Variants
Flexbox itself does not have variants but rather it is complemented or extended by other CSS layout models designed to tackle different types of layouts. The following are key CSS layout models:

- **CSS Grid Layout (CSS Grid)**: While Flexbox is ideal for one-dimensional layouts, CSS Grid is better suited for two-dimensional layouts. Both work together and can even be nested within each other, allowing complex layout designs.
- **Multi-Column Layout**: Best for content that naturally breaks into columns, like magazine layouts or newspaper-style stories.
- **Object-Positioning Layout**: Used to position elements exactly where you want them on screen. Useful for complex fixed or absolute positioning needs.

## Trade-offs
While Flexbox is powerful for a variety of layout scenarios, it is not without its limitations:

- **Limited Support for Layouts in Multiple Directions**: Flexbox was originally designed for one-dimensional layouts and can be challenging to adapt for two-dimensional layouts, necessitating the use of [[grid]] layouts for more complex needs.
- **Lack of Scrollbar Handling**: Flexbox items do not provide a straightforward way to handle overflow content; handling vertical and horizontal scrolling is more complex and not a native feature.
- **Complexity for New Developers**: The rules and properties can be overwhelming for beginners, especially the behavior when multiple flex items have nonzero `flex-shrink` and `flex-grow` values.
- **Browser Support**: Although modern browser support is good, older versions of Internet Explorer and Edge do not fully support Flexbox, which can be a consideration in some development contexts.

## See also
- [[grid]]
- responsive-web-design