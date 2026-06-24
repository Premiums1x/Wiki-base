---
concept: lstm-long-short-term-memory
entity_type: concept
aliases: ["long-short-term-memory", "lstm"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:56Z
---

## Definition
LSTM (Long Short Term Memory) is a type of recurrent neural network (RNN) that extends [[recurrent-neural-network]] by incorporating memory cells and gate mechanisms to address the vanishing gradient problem. It is specifically designed to handle long-term dependencies in sequences of data, such as natural language or time series, and is particularly useful in applications like speech recognition and text generation.

## How it works
In a standard RNN, the input at any given time step is processed and the output is produced based solely on the current input and the hidden state from the previous step. However, this architecture suffers from issues related to vanishing gradients when dealing with very long sequences, which makes it difficult for the model to remember information from earlier time steps. LSTM overcomes this by introducing memory cells that can maintain information over long periods and gates that control the flow of information into and out of these cells.

The three main gates in an LSTM include the **input gate**, which controls how much new information is fed into the cell state, the **forget gate**, which decides how much of the previous cell state's information is retained or forgotten, and the **output gate**, which determines how much of the cell state's information is outputted to the next time step. Together, these gates enable the LSTM to selectively update and preserve information according to what the model has learned from the data.

### Cell State and Gates
- **Cell State** serves as a long-term memory component that keeps track of important information over time. It flows through from one time step to the next, modified occasionally by the gates.
- **Input Gate** modulates the addition of information to the cell state, using a sigmoid layer to decide which values from the current input are updated and an $tanh$ layer to add new candidate values scaled by the sigmoid layer.
- **Forget Gate** controls the elimination of information, also making use of a sigmoid layer to determine which parts of the cell state to keep and which to forget.
- **Output Gate** regulates the information that's output for use in the next time step of the network.

Through this mechanism, LSTM can selectively retain, forget, and incorporate information, which is crucial for processing sequences where earlier input may be relevant much later. [[recurrent-neural-network]] builds on this foundation but lacks such intricate control mechanisms over the flow of information between its layers.

## Variants
Several variants of LSTM have been developed to improve its performance and address specific challenges, such as the **GRU (Gated Recurrent Unit)**. GRU simplifies the LSTM architecture by merging the input and forget gates into a single update gate and removing the cell state. This simplification reduces the number of parameters and computational cost, although it might introduce a trade-off in the model's ability to handle very long-term dependencies compared to full LSTMs.

Other enhancements include **Peephole Connections**, which allow the gates to access the cell state, thereby making more informed decisions about information retention and transmission. **Layer Norm LSTM** introduces normalization within each layer to stabilize gradients during training, thereby improving convergence and robustness.

## Trade-offs
While LSTMs are powerful for handling long-term dependencies, they come with their own set of trade-offs:
- **Complexity and Computational Cost**: The introduction of memory cells and gate mechanisms makes the architecture more complex and computationally expensive compared to basic RNNs. This requires more powerful hardware and longer training times for large datasets.
- **Vanishing/Exploding Gradients**: Even though LSTMs are designed to mitigate vanishing gradients, they are not immune to exploding gradients, which can destabilize the learning process. Techniques like gradient clipping and weight normalization are necessary.
- **Short-Term Memory Weaknesses**: In some cases, particularly with tasks that require rapid adaptation to new information, LSTMs might not perform as well due to the cumulative nature of their memory updates.

## See also
- transformer-architectures trades off with LSTM in modern applications, especially in very large-scale models, as it better handles sequence-to-sequence tasks without relying on recurrent structures.
- language-models often use LSTM as a backbone for generating responses in natural language processing tasks.
- [[recurrent-neural-network]] is the fundamental concept that LSTM builds on and improves.
- natural-language-processing is a domain where LSTMs are commonly applied.