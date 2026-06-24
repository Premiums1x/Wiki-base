---
concept: retrieval-augmented-generation
entity_type: technique
aliases: ["rags", "rag"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:46:12Z
---

## Retrieval Augmented Generation

Retrieval augmented generation (RAG) is an approach that wikilink-wiki-retrieval-augmented-generation combines wikilink-wiki-transformer-architecture, which forms the backbone of many modern large language models, with information retrieval to enhance the generation of outputs, such as text. Specifically, RAG extends the transformer architecture by leveraging a vector-based retrieval system to integrate external knowledge into the generation process.

## How it works
In traditional large language models (LLMs), sequences of text are generated directly based on the understanding gleaned from the massive pretraining data that the model was trained upon. However, these models are prone to generating text that is not grounded in factual information, a phenomenon known as "hallucination." RAG aims to address this by incorporating a retrieval system that finds relevant documents or passages from an external knowledge database. When a query is received, the model encodes it and uses it to query a vector database of documents. The relevant documents are then fed back into the model along with the original query to produce a more accurate response.

The technical workflow involves several steps:
1. **Query Encoding**: When a query is inputted, it is encoded by the transformer model into a vector representation.
2. **Retrieval**: The encoded query is used to search, via some form of vector similarity search, for the most relevant documents in the external knowledge database. This database could be structured as a semantic similarity graph where nodes represent concepts and edges represent relationships between concepts.
3. **Response Generation**: The relevant documents retrieved in the previous step are concatenated with the original query and passed through the transformer model for context-aware generation of a response. This step is where the model reads the provided documents and generates a response leveraging the context from those documents.

This method of combining retrieval with generation aims to improve the factual accuracy and relevance of the model's responses while maintaining the fluency and coherence provided by the transformer's generation capabilities.

## Variants
RAG represents a hybrid approach that can be implemented or adapted in several ways depending on the specific retrieval and generation components used. Variants include:
- **Document-level RAG**: The retrieval step returns documents that are then used to augment the input for the generation stage.
- **Span-level RAG**: Rather than whole documents, this approach retrieves relevant spans (chunks of text), which may be more lightweight and also offer a more precise integration of external knowledge.
- **Hybrid RAG**: This approach integrates pre-trained language models with retrieval agents that can dynamically interact with a knowledge base or the web, providing updated or specific knowledge on demand.

While these variants implement the core principles of RAG, they may differ significantly in terms of complexity, performance, and practical applicability.

## Trade-offs
RAG introduces a promising but nuanced trade-off landscape:
- **Accuracy vs. Efficiency**: Integrating external retrieval systems can enhance the accuracy of the model's outputs by grounding responses in factual information, thereby significantly reducing hallucinations. However, this is at the cost of increased computational and latency overhead due to the need for external knowledge retrieval.
- **Scalability**: The scalability of RAG systems depends heavily on the efficiency of the retrieval system. As the size of the external knowledge base increases, the quality of the retrieved information and the speed of retrieval become critical factors.
- **Resource Dependence**: RAG models rely on an external knowledge retrieval system that must be well-maintained and updated to remain relevant, which introduces an additional layer of complexity and maintenance compared to standalone LLMs.

## See also
- wikilink-wiki-transformer-architecture: The underlying architecture used by RAG in generating outputs.
- wikilink-wiki-supervised-fine-tuning-and-rlaf: Techniques that RAG can optionally leverage to fine-tune its behavior through supervised processes or reinforcement learning.
- wikilink-wiki-rag-traditionalmachinelearning-untraditionalmachinelearning: Traditional and unconventional machine learning approaches that do not incorporate retrieval systems and might exhibit higher hallucination rates.
- wikilink-wiki-rag-probabilistic-models: Machine learning models that rely on probabilistic methods, which can offer a different perspective on information retrieval and text generation.