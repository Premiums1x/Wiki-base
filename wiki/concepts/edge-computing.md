---
concept: edge-computing
entity_type: concept
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:35:16Z
---

## Edge Computing

### Definition
Edge computing is a distributed computing paradigm where data processing and analysis occur closer to the source of data generation. This approach minimizes latency and network bandwidth usage by allowing data to be processed and filtered locally, or at an "edge node," rather than sending it over the network to a centralized data center or cloud environment. It often leverages embedded systems and IoT devices to perform preliminary data processing, machine learning, and analytics.

### How it Works
Edge computing operates by distributing computing resources closer to the edge of the network where data originates. Embedded devices such as microcontrollers (MCUs) and single-board computers (SBCs) can perform initial data processing using local resources. This process involves:
- **Data Collection**: Data is collected from various sensors and devices.
- **Local Processing**: The data is processed locally, possibly using machine learning models (like TinyML) to perform tasks such as anomaly detection or predictive analysis.
- **Decision Making**: Based on the local processing, immediate actions can be taken, such as controlling actuators or sending alerts.
- **Data Transmission**: Only relevant data or summaries are sent to the cloud or a centralized server, reducing data volume and improving efficiency.

### Variants
- **Fog Computing**: A related concept that involves distributing computing, storage, and networking capabilities anywhere along the continuum from the data source to the cloud. Fog computing emphasizes a multi-tiered approach to processing data.
- **Cloudlet**: A small-scale cloud datacenter or edge node close to the point of network access, typically within a few hundred meters or within a single building. 
- **IoT Edge**: Specialized edge computing devices designed for IoT applications, often integrating wireless connectivity and local storage capabilities for processing and transmitting data from connected devices.

### Trade-offs
- **Latency Reduction**: Edge computing drastically reduces the delay between data generation and processing by moving computation closer to the data source.
- **Bandwidth Efficiency**: By performing initial data processing locally, edge computing reduces the amount of data that needs to be transmitted, leading to more efficient use of network resources.
- **Cost**: Higher local hardware costs, as devices need sufficient computational power to process data locally.
- **Scalability**: Compromised scalability when compared to cloud solutions, as edge nodes must be physically deployed.
- **Complexity**: Increased complexity in maintaining and managing edge devices, especially in large-scale deployments.

### See also
Embedded Systems & IoT Real Time Operating Systems (RTOS) MQTT LoRaWAN NB-IoT