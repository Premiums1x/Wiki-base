---
concept: neural-networks
entity_type: concept
aliases: []
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T04:12:05Z
---

## Definition
Neural Networks are computational models inspired by the biological structure and function of the human brain, designed to recognize patterns, learn from data, and make decisions. They extend from [[ai]] as a foundational technology in deep learning, where they are used for various types of complex pattern recognition and decision-making tasks. Neural Networks build on [[machine-learning]], specifically deep learning, by utilizing multi-layer architectures that closely mimic the operation of a biological neural network with interconnected nodes (neurons), enabling hierarchical learning and feature extraction from data.

## How it works
A typical neural network architecture consists of an input layer, one or more hidden layers, and an output layer. Each layer is composed of nodes, or neurons, which are responsible for processing and transmitting information. The nodes in each layer are connected to nodes in adjacent layers by weighted connections, representing the strength or importance of the inputs from the connected neurons. During the learning process, a neural network adjusts these weights to minimize the error between its predictions and the actual outputs.

The process begins with the input layer receiving data. Each input value then moves through the network to the hidden layers, where multiple layers can be used to extract increasingly complex features. For instance, a [[deep-learning]] network that uses convolutional layers might extract edges in an image in the first few layers, shapes in subsequent layers, and finally, objects in the deepest layers. The final output layer combines these extracted features to generate a prediction. This function is typically implemented using an activation function, such as the ReLU (Rectified Linear Unit) or sigmoid function, which introduces non-linearity to the network, allowing it to model complex patterns.

### Forward Propagation
Forward propagation is a key process in a neural network where input data is passed through the network from the input layer to the output layer. This involves calculating the weighted sum of the incoming signals at each node and applying the activation function to this sum. The output of one layer serves as input to the next, enabling information to propagate through the network.

### Backpropagation
Backpropagation is the training process that adjusts the weights of the neural network based on the error in the output. The error is calculated by comparing the network's output to the actual target values. This error is then propagated back through the layers, from the output layer to the input layer, updating the weights in a manner that minimizes the error. This process uses the chain rule from calculus to compute the gradient of the cost function concerning the weights, facilitating the adjustment of the network's parameters through an optimization algorithm, such as gradient descent.

## Variants
Neural Networks have numerous variants designed to address specific types of problems:
1. **Fully Connected Networks**: Each neuron in one layer is connected to every neuron in the next layer, making it suitable for problems without a specific structure in the data.
2. **Convolutional Neural Networks (CNNs)**: Built on fully connected networks but specialize in processing grid-like data such as images. They implement filters to capture local patterns in the data.
3. **Recursive Neural Networks (RNNs)**: Designed to process sequences of data, implementing feedback connections that allow information to persist through time, effectively remembering past inputs.
4. **Transformer Networks**: Improve upon RNNs by eliminating the need for sequence-specific computation through the use of self-attention mechanisms, which compute the importance of each part of the input data for each part of the output data.
5. **Autoencoders**: Aim to learn efficient representations of data (code) by training the network to ignore signal noise. They implement an encoder-decoder structure to compress and decompress data.

## Trade-offs
Neural Networks offer significant advantages but also come with several limitations:
1. **Computationally Intensive**: Training deep neural networks requires substantial computational resources, including memory and processing power, which can be a limiting factor for smaller organizations.
2. **Overfitting**: Neural Networks have a high capacity to model complex functions, making them susceptible to overfitting if not properly regularized or if the network is too complex for the amount of training data available.
3. **Prone to Vanishing/Exploding Gradients**: In networks with many layers, the vanishing gradient problem can prevent sufficient weight adjustments in earlier layers, while exploding gradients can make the training process unstable. These challenges are often mitigated by using techniques like batch normalization or by implementing architectures built on [[deep-learning]] that optimize for these issues, such as RNNs with LSTM units or Transformer networks.
4. **Interpretability Limitations**: The opaque nature of neural networks can make understanding how decisions are made difficult, posing challenges in domains where interpretability is crucial, such as finance or healthcare.
   
## See also
- convolutional-neural-networks
- recursive-neural-networks
- transformer-networks