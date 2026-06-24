---
concept: recurrent-neural-network
entity_type: concept
aliases: ["RNN"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T08:00:27Z
---

## Definition
A Recurrent Neural Network (RNN) is a type of artificial neural network (ANN) designed to handle sequential data and maintain an internal state, or memory, which allows it to utilize past information when processing subsequent data points. This makes RNNs suitable for tasks such as language modeling, speech recognition, and time series prediction. RNNs artificial-neural-networks build on the principles of regular feedforward neural networks (FFNs) by adding loops to the network architecture, allowing information to persist across multiple time steps.

## How it works
### Architecture
The fundamental structure of an RNN includes a sequence of layers where each layer can be connected to the next one in the sequence and to itself. This design recursion allows RNNs to process sequences one element at a time, with each element affecting the output for the subsequent elements. The data flowing through an RNN consists of two types of neurons: input neurons and output neurons. Each neuron maintains an internal state, which influences the output at the next time step.

### Forward Propagation
During training, the forward propagation through an RNN follows these steps:
1. Input feed: The RNN starts processing with the first element of the sequence.
2. Internal state update: The hidden state vector is computed based on the input and the previous hidden state.
3. Output generation: The hidden state is transformed into an output, often through a linear layer followed by a non-linear activation function such as tanh or ReLU.

This process repeats for every element in the sequence, with each step’s output influencing the next.

### Backpropagation Through Time (BPTT)
BPTT is a method used to compute the gradient of the loss function with respect to the parameters of the network during the backpropagation phase. It unrolls the network over time, effectively treating each time step as part of a deep feedforward network to facilitate gradient computation. This extends the normal backpropagation mechanism to account for the temporal nature of the data, allowing the network to learn from the sequence context.

### Challenges and Solutions
RNNs face the vanishing gradient problem, where gradients can decay rapidly during BPTT, making it difficult for the network to learn long-term dependencies. Variants like Long Short-Term Memory (LSTM) and Gated Recurrent Units (GRU) gated-recurrent-units are designed to mitigate this issue by incorporating mechanisms to better control the flow of gradients through time.

## Variants
Several variations of RNN have been developed to tackle the vanishing gradient and related issues:

- **Long Short-Term Memory (LSTM)**: LSTMs [[lstm]] are a special kind of RNN designed to avoid the vanishing gradient problem. They introduce memory cells, which can preserve information over longer periods by controlling the flow of gradients using three types of gates: input gates, output gates, and forget gates. This allows LSTM networks to effectively capture long-term dependencies in the data.
- **Gated Recurrent Units (GRU)**: GRUs are a simpler variant of LSTMs that combine the forget and input gates into a single update gate. They aim to reduce the computational cost while still being able to capture long-term dependencies.
- **Bidirectional RNNs**: Unlike traditional RNNs that process data in one direction, bidirectional RNNs process data in both forward and backward directions. This enables the network to have access to context from both the past and future in a sequence.

## Trade-offs
RNNs artificial-neural-networks require significant computational resources due to their sequential nature and the computational graph required for backpropagation through time. This can be a limiting factor when training large networks on a single machine. Moreover, while LSTMs [[lstm]] and GRUs gated-recurrent-units are designed to handle long-term dependencies more efficiently, they do so by adding more complexity to the network, potentially slowing down the training process and increasing memory usage.

## See also
- artificial-neural-networks
- [[lstm]]
- gated-recurrent-units