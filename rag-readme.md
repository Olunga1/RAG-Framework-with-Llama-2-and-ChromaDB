# RAG Framework with Llama 2 and ChromaDB

This project implements a Retrieval-Augmented Generation (RAG) framework for document question-answering using the Llama 2 model (via Groq) and ChromaDB as a vector store. The system is orchestrated using LangChain.

## Features

- Document loading and parsing (PDF support)
- Text chunking and embedding
- Vector storage using ChromaDB
- Question-answering using Llama 2 (70B model)
- Persistent storage of embeddings for quick reloading

## Prerequisites

- Python 3.7+
- Groq API key

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/rag-llama2-chromadb.git
   cd rag-llama2-chromadb
   ```

2. Install the required packages:
   ```
   pip install chromadb langchain langchain_community sentence_transformers unstructured[pdf] transformers
   ```

3. Set up your Groq API key as an environment variable:
   ```
   export GROQ_API_KEY='your-api-key-here'
   ```

## Usage

1. Prepare your document:
   - Place your PDF file in the project directory.

2. Run the main script:


3. Enter your questions when prompted.

## Project Structure

- `main.py`: The main script that sets up the RAG pipeline and handles user interactions.
- `doc_db/`: Directory where ChromaDB stores the vector embeddings.

## How It Works

1. The script loads a PDF document using Unstructured's PDF loader.
2. The document is split into chunks using LangChain's text splitter.
3. Text chunks are embedded using a Hugging Face embedding model.
4. Embeddings are stored in ChromaDB for efficient retrieval.
5. User questions are processed through a retrieval chain:
   - The question is embedded and similar chunks are retrieved from ChromaDB.
   - Retrieved chunks and the question are sent to the Llama 2 model via Groq.
   - The model generates an answer based on the relevant document chunks.

## Customization

- Adjust the `chunk_size` and `chunk_overlap` parameters in the text splitter to optimize for your documents.
- Experiment with different embedding models by changing the `HuggingFaceEmbeddings` configuration.
- Try different Llama 2 model variants available on Groq by modifying the `model` parameter in `ChatGroq`.

## License

[MIT License](https://opensource.org/licenses/MIT)

## Acknowledgments

- [LangChain](https://github.com/hwchase17/langchain) for the awesome framework
- [Groq](https://groq.com/) for providing access to Llama 2 models
- [ChromaDB](https://github.com/chroma-core/chroma) for the vector store implementation

