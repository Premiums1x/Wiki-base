---
concept: convolutional-neural-network
entity_type: concept
aliases: ["cnn"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:47Z
---

## Definition
A Convolutional Neural Network (CNN) is a type of deep learning algorithm that builds on artificial neural networks (ANNs) to process data that can be represented in a grid-like topology, such as images or video. It excels in capturing spatial hierarchies by applying filters that detect features in the input data, building up from simple to complex patterns. The design of CNNs is heavily influenced by the structure and function of the visual cortex in animals, and it extends the artificial-neural-network|artificial neural network concept by incorporating the spatiotemporal structure inherent to images.

## How it works
CNNs work by applying a series of filters to the input data, which is typically an image or video frame, to extract features at various levels of complexity. These processes occur through several key stages:

### Input Layer
The input layer receives the raw data; in the case of images, this is the raw pixel values.

### Convolutional Layer
In this layer, multiple filters (also known as kernels) are applied to the input data to detect various features. Each filter is responsible for detecting a specific type of feature, such as edges or textures. Convolutions are performed by sliding these filters over the input data, computing the sum of the element-wise products at each location. This process helps in extracting meaningful features from the input data without being affected by the translations (shifts in position) within the image, a property known as translation invariance. 

### Pooling Layer
Following the convolutional layer, a pooling layer is often applied. The most common type is max pooling, which down-samples the input representation by reducing its dimensionality. This step significantly cuts computational costs and theoretically preserves the most discriminative features. Pooling acts by reducing the spatial size of the representation, distilling key elements captured during the convolution process.

### Fully Connected Layer
After the convolution and pooling layers, the data typically goes through a fully connected layer, where every neuron touches every other neuron. Here, the features are passed through and used to classify the input into one of the target classes. This stage builds on the feature extraction performed in earlier layers to predict a class or a set of classes for the input data.

### ReLU (Rectified Linear Unit)
Between the convolutional and/or pooling layers, and prior to passing the data to the fully connected network, an activation function like ReLU (Rectified Linear Unit) is often applied. ReLU introduces non-linearity, enabling the network to learn more complex functions. This is critical as it helps the network approximate any non-linear function.

These layers operate upon each other sequentially, with the output of one serving as the input for the next, until the final classification or prediction is made.

## Variants
There are several variants and extensions of CNNs, each optimized or designed for specific improvements over the traditional architecture:
- **Dilated Convolution (Atrous Convolution)**: This variant implements an optimized structure of convolution that effectively increases the receptive field of the model without adding parameters or increasing computational cost. It trades off complex computations in the convolution process with higher spatial resolution (i.e., capturing more fine-grained changes) and thus can enhance the detection accuracy of CNNs.
- **Inception Network**: Known for implementing CNN architectures where filters of varying sizes are stacked together in parallel, this network design proves faster yet is as capable as traditional CNNs. It is an implementation of the fundamental CNN concept, aiming to explore multiple levels of abstraction in parallel.
- **Residual Network (ResNet)**: Built on the idea of adding residual connections across layers, which can help mitigate the degradation problem that gets worse as the depth of a network is further increased. ResNet introduces new architectures that are deeper and potentially wider, thus optimizing performance at the cost of computational complexity and an increase in the network depth over traditional CNNs.

## Trade-offs
The use of CNNs also comes with several trade-offs:
- **Parameter Sensitivity**: CNNs can be highly sensitive to selection of hyperparameters, particularly concerning the hyperparameters involving structure design such as filter size, number of filter layers, and number of filters in each layer.
- **Interpretability**: CNNs are often criticized for their "black box" nature, meaning that their decision-making process can be hard to interpret, thus hindering usability in applications where explainability is a key requirement.
- **Resource Intensive**: While CNNs are powerful, they are computationally expensive, especially for real-time applications. The accumulation of operations, including convolutions, pooling, and fully connected layers, can require significant computational resources.

## See also
For related concepts, consider exploring:
- [[artificial-neural-network]]
- [[transformer-architecture]] (for deeper understanding in sequence data processing by another deep learning architecture)
- depth-of-networks