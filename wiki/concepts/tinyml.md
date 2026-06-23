---
concept: tinyml
entity_type: technique
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:35:25Z
---

## Definition
TinyML, short for Tiny Machine Learning, is a subfield of machine learning that focuses on developing and deploying machine learning models on resource-constrained devices such as microcontrollers and other small embedded systems. These systems typically have limited computation, memory, and power resources but are widely used in Internet of Things (IoT) applications, wearable devices, and other real-time systems.

## How it works
TinyML integrates machine learning models into embedded systems, which are often powered by microcontrollers with very little processing power and limited memory (often under 1MB of RAM). This integration is accomplished by optimizing machine learning algorithms to fit these constraints. This involves:
- **Model Compression**: Reducing the complexity of models through techniques such as pruning, quantization, and compression to fit into the constrained environments.
- **Inference Mechanisms**: Implementing lightweight versions of machine learning frameworks such as TensorFlow Lite or Edge Impulse, which are specifically designed to run efficiently on microcontrollers.
- **Energy Efficiency**: Designing models that efficiently use power, often at the expense of computational accuracy, to prolong the battery life of embedded devices.

## Variants
- **TinyML on Microcontrollers**: Using machine learning inference on microcontrollers like ARM Cortex-M series, ESP32, or Arduino-compatible devices.
- **Edge AI**: Embedding AI capabilities on the edge of the IoT network, close to where data is generated.
- **IoT Machine Learning**: Integrating machine learning into IoT devices to enable smarter, more responsive operations, often utilizing the edge computing paradigm.
- **Tiny Deep Learning**: A subset of TinyML that specifically explores the deployment of deep learning models on resource-constrained devices.

## Trade-offs
TinyML strikes a balance between model complexity and device constraints, but several trade-offs and limitations exist:
- **Accuracy vs. Efficiency**: There is often a trade-off between the accuracy of the ML model and the efficiency required by the embedded device. Pruning and quantization can reduce model size but may affect accuracy.
- **Model Deployment**: The process of deploying complex ML models onto tiny devices requires significant optimization for effective use.
- **Power Consumption**: TinyML models must be designed to run efficiently to consume less power and extend battery life of the device.
- **Computation Limitations**: While TinyML pushes the boundaries of what can be done with limited computational power, it is still constrained by the hardware, limiting the complexity of tasks that can be tackled.

## See also
[[embedded-systems]], MCU, IoT Architecture, LoRaWAN, ESP32, STM32, Real-Time Operating Systems (RTOS)