---
concept: react-native
entity_type: concept
aliases: []
sources: ["raw\\mobile_development.md"]
confidence: high
created_at: 2026-06-23T04:14:19Z
---

## React Native

### Definition
React Native is a JavaScript framework created by meta-fb (originally Facebook) that allows developers to write mobile apps using React and JavaScript (or TypeScript). React Native aims to build high-performance, native-like mobile applications across iOS and Android platforms with a single codebase, extending the capabilities of React, a JavaScript library for building user interfaces.

### How it Works
React Native apps are built using JavaScript with a JSX syntax, a syntax extension for JavaScript, which allows for writing HTML-like elements directly within JavaScript code. The framework uses the React component architecture, where components are the building blocks of UI hierarchy. Components can be custom-defined and reused, allowing developers to break down the UI into manageable and reusable pieces.

In React Native, the JavaScript code is compiled into platform-specific code (Android or iOS) just in time (JIT) or ahead of time (AOT) through tools like the Hermes JavaScript engine. This compiled code communicates with native components through the JSI (JavaScript Interface) or native modules, which are actual native code components that the app uses to access the device's hardware and system services. This process, known as "bridging," allows for a seamless integration of JavaScript logic with native functionality.

Unlike Flutter, which uses its own rendering engine to draw components, React Native's "native components" approach ensures that the code runs efficiently by interfacing directly with the specific widgets and UI elements provided by the iOS or Android platforms. Each component maps to a native UI element, so the end result is a native application that performs as well as one written in Swift or Kotlin for iOS and Android, respectively. This approach optimizes the performance of web developers who are already familiar with React.

### Variants
React Native supports multiple ways to structure applications, including the basic component architecture mentioned above. In addition, the framework offers several libraries and extensions to enhance its capabilities, such as:

- **Expo**: A platform built on top of React Native that provides a set of tools and services to make the development process easier, especially for prototyping and managing the development environments. Expo optimizes its own project structure and provides a simplified setup for critical services such as authentication, monitoring, and remote configuration.

- **Redux** redux and **MobX**: These state management libraries can be utilized within a React Native app to effectively manage application state. While not part of React Native itself, they are commonly integrated to handle complex state logic and provide a single source of truth for user data and interactions.

### Trade-offs
React Native presents various trade-offs that must be considered depending on the requirements and priorities of a given application:

- **Performance**: Although React Native offers high development efficiency, its performance may not always match the lowest level optimizations achievable with native development frameworks. Certain performance-critical operations may require knowledge of native module development due to the bridge's overhead. This is in contrast to native languages [[swift]] and [[kotlin]] which directly interact with the hardware and system APIs.

- **Complexity**: The bridge that connects JavaScript to native components introduces additional complexity and adds overhead. Managing state, lifecycle events, and concurrency can be more intricate compared to native development, especially when dealing with complex or highly interactive interfaces.

- **Tooling**: While React Native has powerful tools, some features may not be as sophisticated or as well integrated as their native counterparts. For instance, React Native’s debugging process can differ from native debugging, and accessing some iOS-specific APIs might require more effort due to the need for proper bridging.

### See also
- [[flutter]] - Another popular JavaScript-based mobile application framework
- [[swift]] - The primary programming language for iOS development
- [[kotlin]] - The recommended language for Android development