---
concept: react-native
entity_type: concept
aliases: []
sources: ["raw\\06-mobile-development\\mobile_development.md"]
confidence: high
created_at: 2026-06-24T07:58:14Z
---

## Definition
React Native is a JavaScript framework developed by Meta (previously Facebook) for building mobile applications for both ios and android. It extends the [[react]] library by allowing developers to use JavaScript and reusable JS components to render natively on the mobile device. This approach enables developers to write code once and run it across multiple mobile platforms.

## How it works
React Native operates by leveraging React's component model, but instead of rendering UI on the web, it renders UI directly to the mobile device's native components. Developers write the main logic of the app in JavaScript and TypeScript, with a React-like component structure where each component's UI is described using proprietary React elements and tags. These components are then translated into native device interface elements through a runtime bridge. The bridge acts as a mediator, translating the commands from the JavaScript code into native calls. This method contrasts with web or desktop React applications, which render UI elements using HTML and JavaScript alone.

React Native employs a mechanism known as the JavaScript Core Interface (JSI), an upgrade from the traditional bridge, to interface with JavaScript within the runtime. JSI enables a more direct communication between the React Native JavaScript environment and the native platform's capabilities, significantly improving performance by minimizing the overhead associated with JavaScript-to-native communication.

React Native apps are built following the component-based architecture, similar to web development using React, where developers write components that encapsulate both the layout and behavior of a screen or part of a screen. These components make API calls, store data, and render various UI elements such as buttons, text, images, and complex layouts.

## Variants
Several variants of React Native exist to optimize or extend its core functionalities:
- **EXPO**: A toolchain and a framework by the Expo organization that uses React Native to build high-quality native-rich applications continually with JavaScript. Expo builds on React Native by offering a set of libraries that simplify common mobile development tasks like push notifications, user authentication, and access to device features without requiring the native developer tools or a lengthy development cycle.
- **React Native Elements**: This library extends the functionality of React Native by adding highly customizable and easy-to-use components that comply with Material Design and iOS guidelines.
- **React Native Paper**: A design system for building fast and beautiful user interfaces for React Native apps that implements material design principles from Google.

## Trade-offs
Implementing React Native presents several trade-offs compared to native development:
- **Performance**: While React Native can achieve performance close to native apps, it may not match the speed of fully implemented native applications due to the overhead involved in translating JavaScript to native calls. This lag can be mitigated by using performance-intensive JavaScript components that rely heavily on native modules.
- **Accessibility**: React Native apps may not fully comply with platform accessibility standards as seamlessly as native apps do, since front-end code runs on JS threads instead of native threads dedicated to providing accessibility features.
- **Platform-Specific Features**: React Native developers must often write platform-specific code to integrate advanced features that are not supported natively, like certain hardware features or platform-specific SDKs, leading to additional development time.