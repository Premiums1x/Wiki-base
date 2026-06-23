---
concept: osi-model
entity_type: concept
aliases: []
sources: ["raw\\cybersecurity.md"]
confidence: high
created_at: 2026-06-23T04:12:28Z
---

## Definition
The OSI (Open Systems Interconnection) model is a conceptual framework that divides network communication into seven layers: Physical, Data Link, Network, Transport, Session, Presentation, and Application. It provides a common vocabulary for describing, understanding, and troubleshooting network communications. This model helps in standardizing network protocols and performs functions such as ensuring accurate and efficient communication among networked computers. The OSI model is foundational in understanding network architecture; it does not implement protocols itself but provides a framework for developing and maintaining standards such as those defined within the tcp-udp protocols, which relImplements the OSI model for practical communication processes.

## How it works
The OSI model functions by breaking down the intricacies of network communication into seven distinct layers. Each layer is responsible for a specific aspect of the communication process and interacts with the layers immediately adjacent to it. Here's a brief overview of each layer's operation and functions:

- **Physical Layer:** This layer is responsible for the physical transmission of raw bit streams over a physical medium. It specifies the electrical, mechanical, and functional interfaces necessary to transmit and receive digital data. For example, it includes protocols like Ethernet and Token Ring, which define how the data is transmitted over network cables.
  
- **Data Link Layer:** It manages the flow of data between nodes across a physical link. It bunches bits into frames, and each frame includes the source and destination addresses. This layer performs flow control and error detection. A well-known example is the Ethernet protocol, which is used for transferring information over the internet and is one of the varieties of 802.11 standards.
  
- **Network Layer:** Its primary function is data routing from source to destination. It performs logical addressing (using IP addresses) and selects the physical path a data packet will travel on its route to the destination. This layer decides on the best path for data packets, taking into account cost, delay, and reliability.
  
- **Transport Layer:** This layer ensures that the data the sender sends is accurately received and understood by the receiver. It is responsible for segmenting and reassembling messages, providing reliable data transfer (TCP) or unreliable (UDP). TCP uses reliable connection establishment and closure mechanisms known as the three-way handshake and four-way handshake, respectively, ensuring that each segment of data is accurately delivered.
  
- **Session Layer:** This layer establishes, manages, and terminates sessions between applications. It takes care of overall communication management, including functions such as connection setup, managing data exchange, and performs session synchronization.
  
- **Presentation Layer:** This layer handles the translation of data into a form that applications can understand. It performs encryption, compression, and is responsible for the syntax and semantics of the information transmitted. Examples include the SSL protocol, which uses encryption to securely transmit data over a network.
  
- **Application Layer:** It provides network services to applications and interactions between end-users and the network. This layer is directly associated with user applications and is responsible for providing network services to the user. It includes protocols like HTTP for web browsing, FTP for file transfer, and SMTP for email communication.

The layers operate independently of each other, but they all work together to ensure secure and effective communication. Information flows from the upper layers to the lower layers and from the receiving end, from lower layers to upper layers towards the Application Layer.

## Variants
Although the OSI model is conceptual, actual implementations vary globally. Several network protocols and architectures have been developed to serve specific network communication requirements, and they often operate in ways that closely mirror the OSI model's structure. Variants of the OSI model that are commonly implemented include:

- TCP/IP Model: Widely used in the internet, it includes four layers rather than seven and combines several OSI layers into one. For example, it merges the OSI model’s Application, Presentation, and Session layers into its Application Layer.
- TCP and UDP Protocols: These protocols are implementations in the Transport Layer, with TCP providing reliable, connection-oriented service and UDP providing connectionless, unreliable but faster service.
- HTTP and FTP: These are examples of protocols that operate above the Application Layer and provide network service to users.
- Various wireless standards: These mimic the Data Link Layer's functionality while adapting to wireless media.

## Trade-offs
Implementing a comprehensive OSI model comes with several trade-offs and limitations, including:

- **Complexity and Overhead:** The OSI model’s detailed layers can lead to increased complexity and potential overhead in the protocol stack. It requires more sophisticated hardware and software implementations compared to simpler models, such as TCP/IP.
  
- **Implementation Focus:** The OSI model’s presence may lead to a strong focus on each layer in isolation, potentially overly complicating the inter-layer interdependence. The TCP/IP model, for instance, is more straightforward as it merges several OSI layers into its layers for practicality.
  
- **Historical Relevance and Modern Practices:** Modern network architectures, such as those used in the internet, might not adhere strictly to the OSI model, making it less relevant in explaining today’s network implementations.

## See also
- tcp-udp - Contradicts the OSI model by not strictly adhering to its layer specifications.
- 802.11 - Relies on the Data Link layer of the OSI model but diverges by specializing in wireless standards.