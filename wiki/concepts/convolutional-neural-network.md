---
concept: convolutional-neural-network
entity_type: technique
aliases: ["卷积神经网络", "CNN"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:33:20Z
---

## Definition
A Convolutional Neural Network (CNN) is a class of [[deep-learning]] artificial neural networks, designed specifically for processing data with a grid-like topology, such as images, where local connections and shared weights are key components for capturing spatial hierarchies. It builds on the artificial-neural-network structure, extending its capabilities by incorporating convolutional layers that are adept at handling input data with a known, local connectivity pattern. This makes CNN particularly effective for tasks like image recognition and object detection.

## How it works
Convolutional Neural Networks function by estimating and learning a set of filters that are applied to the input data to extract features. Each filter convolves across the input data to produce feature maps, which represent localized features at different scales and locations. This process is repeated with different filters, allowing the network to capture a hierarchy of increasingly complex features. Commonly, convolution operations are followed by pooling to reduce the spatial size of the representation, thus reducing the number of parameters and computational load, and introduce translation invariance for larger regions.

The structure of CNN generally includes:
1. **Convolutional Layer**: Processes the input data through convolution and applies learned filters. This layer utilizes the principle of local connectivity to efficiently detect local patterns, such as edges, colors, and textures.
2. **Activation Layer**: Thereafter, an activation function, such as ReLU, is applied to the output of the convolutional layer to introduce non-linearity. This helps the network capture more abstract representations of the input data.
3. **Pooling Layer**: Often integrated after the activation, it performs a down-sampling operation, wherein only the most prominent features from each sub-region are preserved. This also plays a role in invariantness, allowing for scalability.
4. **Fully Connected Layer**: Towards the output, the data is flattened and passed through one or more fully connected layers that make the final classification or regression decision based on the trained parameters.

## Variants
The core concept of the CNN has led to various improvements and adaptations:
- **LeNet-5**: One of the earliest implementations designed particularly for handwritten digit recognition.
- **AlexNet**: Known for its success in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2012, this enhanced model had noticeable architectural differences from previous networks.
- **VGGNet**: Another variant that led the ILSVRC competition, noted for its architecture simplicity, where the network depth was increased while keeping the complexity manageable.
- **ResNet**: Introduced residual blocks to facilitate deeper networks by using skip connections, which enhance the network's ability to learn from increasingly deep layers.

These variants optimize upon the base CNN concept by improving upon computational efficiency, stability during training, and capacity to capture information from very deep models.

## Trade-offs
The design of CNNs has trade-offs that are a necessary compromise for achieving high performance in specific applications. For instance:
- **Parameter efficiency**: A major benefit of CNNs, especially compared to fully connected networks, is their ability to deal with large datasets efficiently due to the parameter sharing in convolutional layers. However, very deep networks can still contain an enormous number of parameters.
- **Translation Invariance vs. Location Sensitivity**: Through the use of pooling layers, CNNs become robust to alterations in the location of an object within the image. However, this comes at the cost of potentially losing important spatial details that are sensitive to object positioning.
- **Complexity and Overfitting**: Deep networks are prone to overfitting if not designed carefully, requiring careful consideration of dropout, L2 regularization, and data augmentation techniques. Additionally, training deep networks can be computationally intensive and require extensive computational resources.

## See also
- image-recognition
- object-detection