---
concept: edge-computing
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:54Z
---

## Definition
Edge Computing is a distributed computing paradigm that processes data near the source of data generation, minimizing latency and saving bandwidth. It is a specific implementation of the broader concept of Distributed Computing, deploying computing resources at the edge of the network wikilink rel-implements distributed-computing to handle tasks locally before sending only critical or aggregated data back to central cloud servers. Edge Computing builds on the principles of Cloud Computing by bringing computational capabilities closer to the end-users wikilink rel-extends cloud-computing.

## How it works
The Edge Computing model operates through a layered architecture which includes devices, gateways, and cloud services. Data from sensors or other generating devices is initially processed locally through an edge device or gateway. This middleware layer can perform initial filtering, real-time analytics, local storage, and basic AI processing such as TinyML wikilink rel-implements tiny-ml for inference. By processing closer to the source, it reduces the load on the network and the cloud, thereby minimizing latency and enhancing response times.

The technology involves various steps:
1. **Data Collection**: Sensors or IoT devices collect data.
2. **Data Processing at the Edge**: Edge nodes process data locally. This phase can vary from minimal filtering and aggregation to more complex real-time analytics.
3. **Decision Making**: Edge nodes make local decisions based on processed data, running algorithms like machine learning models locally to enable quick response.
4. **Data Communication**: After processing, the edge node may communicate with cloud servers to send aggregated data or more critical insights for further analysis or storage.
5. **Feedback Loop**: Centralized cloud services can also send down updates or instructions to edge nodes, maintaining a bidirectional relationship.

Communication between edge nodes and the cloud is often done via established protocols such as MQTT or CoAP [[wikilink rel-implements mqtt] and [wikilink rel-implements coap]], which are chosen for their low power consumption and minimal payload.

## Variants
Edge Computing has evolved into several forms and implementations based on the context:
- **AI at the Edge**: Utilizing local AI inference capabilities, this variant extends the core principle of edge computing by performing advanced analytics or decision-making directly on edge devices.
- **Mobile Edge Computing (MEC)**: This form specifically targets mobility and connectivity in telecommunications, utilizing edge computing to reduce network congestion and improve user experience in mobile applications and services.
- **Fog Computing**: A variant that further extends the idea of edge computing, distributing computing resources across multiple layers between the cloud and edge devices. It involves placing nodes across the entire network topology to optimize data processing closer to the data source.
- **5G Edge Computing**: With the advent of 5G, there is increased focus on optimizing edge computing capabilities within 5G networks to provide ultra-low latency services.

## Trade-offs
Implementing Edge Computing introduces several trade-offs and considerations:
- **Complexity of System Architecture**: The deployment of edge computing requires a more complex system architecture compared to traditional centralized computing.
- **Cost of Edge Infrastructure**: Besides the initial cost of setting up edge devices, ongoing maintenance and power consumption add to the operational costs.
- **Security and Data Privacy**: Since sensitive data is processed locally, securing edge devices and ensuring data privacy become critical, wikilink rel-trades-off security.
- **Scalability**: Traditional cloud infrastructures are more easily scalable compared to distributed edge computing systems, which may face challenges when scaling up or down depending on demand.
- **Dependence on Underlying Technologies**: Edge computing depends on the reliability and performance of edge devices, connectivity technologies, and communication protocols wikilink rel-depends-on iot.

## See also
- wikilink distributed-computing
- wikilink cloud-computing
- wikilink tiny-ml
- wikilink mqtt
- wikilink coap
- wikilink iot