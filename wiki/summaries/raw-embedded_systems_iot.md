---
source: raw\embedded_systems_iot.md
source_type: article
source_hash: sha256:88b3651edf192edc117d4682fb9a33c79b63eaae5c8a0a9a8c034d4922ee758c
compiled_at: 2026-06-23T03:31:17Z
chunk_count: 1
---

## Key claims
- 嵌入式系统是针对具体应用优化的专用计算机系统。
- 物联网通过网络将嵌入式设备连接，实现智能管理。
- 以上系统通常使用微控制器来执行特定功能。
- 物联网通信技术包括 MQTT、CoAP、LoRaWAN 和 NB-IoT 等，适用于不同网络环境。
- 边缘计算可减少数据中心的带宽占用和响应延迟。

## Methodology
本文主要采用了描述性语言来介绍嵌入式系统和物联网的硬件基础、软件开发方法及网络架构。文中没有使用实验研究或数据挖掘等特殊方法。

## Results
- MCU 是嵌入式系统的关键组件。
- 多种通信总线（如 UART, I2C, SPI）被广泛使用在嵌入式硬件中。
- 特定应用需使用适当的协议和操作系统，而且经常会用到 C/C++ 或 Rust 等编程语言。
- IoT 系统采用了多种轻量级和低功耗通信协议，如 MQTT 和 CoAP。
- 边缘计算和 TinyML 技术在 IoT 设备上提供直接的数据处理和 AI 推理。

## Concepts
嵌入式系统, MCU, STM32, ESP32, Arduino, UART, I2C, SPI, GPIO, C/C++, Rust, 裸机开发, RTOS, FreeRTOS, RT-Thread, MQTT, CoAP, LoRaWAN, NB-IoT, 边缘计算, TinyML