---
concept: react-native
entity_type: technique
aliases: []
sources: ["raw/mobile_development.md"]
confidence: high
created_at: 2026-06-23T03:36:08Z
---

## Definition
React Native is a JavaScript framework developed by Meta (formerly Facebook) designed for building native mobile applications for both iOS and Android platforms. It leverages React, Facebook's popular JavaScript library for building user interfaces, to create mobile applications that use the device’s native components through a bridge mechanism, thereby enabling a unified development workflow while providing native performance.

## How it Works
React Native applications are developed primarily with JavaScript and TypeScript. At its core, React Native utilizes a bridge (or in newer versions, JavaScript Interface (JSI)) to communicate between the JavaScript code and the native platform's components. The framework translates the JavaScript code into native code at runtime, which allows for true native performance without writing platform-specific code from scratch. This process leverages the vast ecosystem of React and JavaScript tools and community.

React Native uses the declarative paradigm popularized by React, facilitating a smooth learning process for developers already familiar with React. Here’s a technical breakdown:

- **Bridge (JSI in newer versions)**: Translates JavaScript commands to native actions.
- **Components**: React Native apps are built using components, which can correspond to platform-specific components, ensuring native-like behavior and performance.
- **JavaScript**: Handles the logic and state management, with native modules for essential system-level interactions.

## Variants
React Native, due to its open-source nature, has seen several forks and alternative implementations:

- **Expo**: A toolchain that extends React Native and simplifies the development process by abstracting away native builds and offering cloud-backend services. Expo also offers an app containing a lightweight, configurable runtime to test Apps on supported devices.
- **Capacitor/Quasar/Cordova**: Similar cross-platform solutions offering their own unique sets of tools for building mobile applications and sharing codebases between different platforms.
- **Runtimes and Builder Tools**: Various customized runtimes and build workflows, such as Visual Studio Code extensions or React Native CLI enhancements, can streamline development processes or enable specific use cases.

## Trade-offs
Using React Native comes with its unique set of trade-offs and limitations to consider:

- **Performance**: While React Native aims for native performance, performance issues can arise due to the communication overhead between the JavaScript environment and the native threads. However, the newer JSI mechanism aims to alleviate some of these concerns.
- **Dependency on JavaScript**: Developers are bound by the capabilities and limitations of JavaScript for handling complex tasks, which might be more efficiently handled in native languages like Swift or Kotlin.
- **Developer Teams**: Requires teams to have JavaScript proficiency, which might not align with everyone's strengths, and the need for a deep understanding of JavaScript ecosystem tools.
- **Advanced Native Features**: Certain features, particularly those requiring low-level access (e.g., camera services, sensor data), may require native modules, decreasing cross-platform code sharing.

## See also
Flutter, [[swift]], SwiftUI, Jetpack Compose, Cordova, Expo