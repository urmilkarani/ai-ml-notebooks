# Healthcare RAG-based AI Solution

## Business Context
The medical field is constantly evolving, with new research, treatments, and guidelines emerging every day. Medical professionals face significant information overload when trying to stay updated. A Retrieval-Augmented Generation (RAG) based AI solution can provide quick and accurate access to specialized medical knowledge, assisting in diagnostics and treatment planning.

## Objective
Develop a RAG-based AI solution using the Merck Manuals as the knowledge base. This system will allow users to ask medical questions and receive evidence-based answers with citations, improving the efficiency and accuracy of medical information retrieval.

## Data Description
The primary data source is the Merck Manuals (Professional Version), a widely respected medical resource. The data is processed into chunks and stored in a vector database for efficient retrieval.

## Key Technologies Used
- Python
- OpenAI GPT (or other LLMs)
- LangChain
- Vector Databases (e.g., Pinecone, Chroma)
- RAG (Retrieval-Augmented Generation)
- Data Preprocessing and Chunking

## Implementation Details

### System Architecture
The solution is built on a **Retrieval-Augmented Generation (RAG)** pipeline, which enhances LLM responses by retrieving relevant documents from a trusted medical knowledge base before generating an answer.

### Core Components
- **Orchestration**: Utilized the **LangChain** framework to manage prompt templates, retrieval chains, and LLM interactions.
- **Vector Storage**: Implemented **ChromaDB** as the local vector database to store and query indexed medical content.
- **Models**:
  - **LLM**: Integrated **Mistral-7B-Instruct** for generating high-quality medical summaries.
  - **Embeddings**: Used **HuggingFace** sentence-transformers to convert text chunks into dense numeric vectors.

### Implementation Strategy
- **Knowledge Source**: The system indexes over **4,000 pages** of the Merck Manuals.
- **Indexing Optimization**: Implemented a multi-vector store approach with three varying chunk sizes (**500, 1000, 2000 characters**) to evaluate retrieval quality across different granularities.
- **Accuracy**: By including citations and evidence from the manual, the system significantly reduces LLM "hallucinations" in a critical healthcare context.
