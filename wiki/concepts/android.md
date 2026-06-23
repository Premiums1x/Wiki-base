---
concept: android
entity_type: concept
aliases: []
sources: ["raw/mobile_development.md"]
confidence: high
created_at: 2026-06-23T03:35:49Z
---

## Definition
Android is a mobile operating system based on a modified Linux kernel and other open-source software. Developed primarily by Google, Android is designed for touch screen mobile devices such as smartphones and tablets. It is a key part of Google's mobile and desktop application services, providing a user-friendly interface and a wide array of applications for various use cases.

## How it Works
Android handles the basic operations of a mobile device, including the user interface, app management, hardware control, and internet connectivity. The core components of Android include the Linux kernel, Native Libraries (including the Android Runtime), the Application Framework, and the Application Layer. 

- **Linux Kernel**: Provides the core services such as device drivers, process management, and high-level power management.
- **Native Libraries**: These include the hardware abstraction layer, multimedia libraries, browser engine, and others, enabling features like graphics rendering and web browsing.
- **Android Runtime**: Consists of the ART (Android Runtime), which optimizes application performance and energy consumption.
- **Application Framework**: Offers various components to simplify application development, such as Activity Manager, Location Manager, Resource Manager, and telephony managers.
- **Application Layer**: The uppermost layer where all user applications run, including pre-installed apps like the web browser, email, calendar, and others, as well as user-installed applications.

## Variants
There are several variants and implementations of Android, primarily distinguished by their customization levels:

- **Stock Android (Pure Android)**: Directly developed and released by Google, it is free from additional bloatware and is used as the base system for Pixel devices.
- **Android with OMS (Open Mobile End) UI**: A version modified by OEMs (Original Equipment Manufacturers) to incorporate their own software and services.
- **UI Skins**: Customized UI skins developed by manufacturers like Samsung (One UI), Huawei (EMUI), and Xiaomi (MIUI), to provide a unique user experience.
- **Custom ROMs**: Developed by the community, these come with customized features, performance tweaks, and support beyond the official lifecycle of specific devices.

## Trade-offs
### Pros:
1. **Open Source**: The open-source nature invites contributions from developers worldwide, enhancing features and security.
2. **Compatibility and Interoperability**: A wide range of apps on the Google Play Store ensures a broad ecosystem of application support.
3. **Customization**: Offers a high degree of flexibility and customization through different skins and ROMs.

### Cons:
1. **Security Risks**: The openness and fragmentation can lead to security vulnerabilities if not properly managed.
2. **Fragmentation**: Various versions of Android are running on different devices, complicating developer support and user experience due to varying feature availability.
3. **Bloatware**:制造商可能会在其设备上加载额外的应用程序和服务，这可能会干扰用户体验并消耗资源。

## See also
移动开发  
原生开发  
跨平台开发  
iOS  
[[react-native]]  
Flutter