# 移动应用开发 (Mobile Development)

移动开发是指为智能手机、平板电脑等移动设备编写应用程序的过程。目前，移动操作系统主要被 Apple 的 iOS 和 Google 的 Android 所瓜分。

## 1. 原生开发 (Native Development)

原生开发是指针对特定的移动平台使用官方推荐的语言、工具和 SDK 进行开发。原生应用能获取最佳的性能和最完整的系统级 API 支持。

### iOS 开发
*   **开发语言**：**Swift**（现代、安全、快速，目前主流），Objective-C（老旧项目仍在使用）。
*   **核心框架**：
    *   **UIKit**：传统的命令式 UI 框架。
    *   **SwiftUI**：Apple 推出的一款声明式 UI 框架，支持实时预览，开发效率极高。
*   **开发工具**：Xcode（只能运行在 macOS 系统上）。

### Android 开发
*   **开发语言**：**Kotlin**（Google 官方推荐的首选语言，支持与 Java 互操作），Java（老旧项目使用）。
*   **核心框架**：
    *   **Android SDK / View System**：传统布局（XML + Java/Kotlin）。
    *   **Jetpack Compose**：Android 的声明式 UI 工具包，思想类似于 React 和 SwiftUI。
*   **开发工具**：Android Studio（基于 IntelliJ IDEA 深度定制）。

---

## 2. 跨平台开发 (Cross-Platform)

为了降低研发成本，实现“一套代码，多端运行”，跨平台技术在企业开发中应用极广。

### Flutter
*   **开发者**：Google。
*   **开发语言**：**Dart**。
*   **技术原理**：Flutter 不使用平台的原生组件，而是拥有自己独立的高性能渲染引擎（Skia / Impeller），直接通过 GPU 绘制每一个像素。这保证了在 iOS 和 Android 上高度一致的视觉表现，且拥有接近原生的帧率（60FPS/120FPS）。

### React Native (RN)
*   **开发者**：Meta (Facebook)。
*   **开发语言**：**JavaScript / TypeScript**。
*   **技术原理**：使用 JavaScript 编写逻辑，UI 仍然基于 React 的组件化思想，但是在渲染时通过桥接（Bridge）或新版的 JSI 机制将 JS 组件映射为各平台的**原生组件**。对于熟悉 Web React 开发的程序员非常友好。

---

## 3. 移动端核心挑战

*   **生命周期管理**：移动端内存和电量极其宝贵，系统会随时暂停或杀死后台应用。开发者必须妥善处理应用的休眠、激活、销毁状态。
*   **屏幕适配**：需要适配不同尺寸、分辨率、刘海屏、折叠屏等设备。
*   **应用商店发布**：iOS 应用发布必须通过 Apple App Store 极其严格的人工审核；Android 发布需要对接国内各大安卓渠道以及海外的 Google Play Store。

