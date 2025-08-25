# RAG-based Enterprise Search System

This project implements a **Retrieval-Augmented Generation (RAG)** system for enterprise document search using PDF ingestion, semantic search with FAISS, and answer generation via Google Gemini. The system enables users to query large collections of documents and receive contextually relevant, AI-generated answers.

---

## Features

- **PDF Ingestion:** Extracts and splits text from PDF files into manageable chunks.
- **Semantic Embeddings:** Uses SentenceTransformers to generate vector embeddings for each text chunk.
- **Vector Search:** Stores embeddings in a FAISS index for fast similarity search.
- **Metadata Tracking:** Keeps track of source, page, and chunk for each text segment.
- **RAG Querying:** Retrieves top relevant chunks and uses Gemini (Google Generative AI) to generate answers based on retrieved context.
- **Extensible:** Easily add more documents or support other file types.

---

## Requirements
- Python 3.8+
- [Google Generative AIPython SDK
- [PyPDF2](https://pU](https://pypi.org/project/faiss-cpupi.org/projectdencies using:

```bash
pip install google-generativeai pypdf2 faiss-cpu sentence-transformers numpy
```
## How It Works

### 1. PDF Ingestion

- The system reads a PDF file using **PyPDF2**.
- Each page's text is extracted and split into chunks (default: 1000 characters, preserving sentence boundaries).
- Each chunk is embedded into a vector using a pre-trained **SentenceTransformer** model (`all-MiniLM-L6-v2`).
- Embeddings are stored in a **FAISS** index for efficient similarity search.
- Metadata (source file, page number, chunk index) is stored for traceability.

### 2. Querying

- User submits a natural language query.
- The query is embedded using the same **SentenceTransformer** model.
- FAISS retrieves the top-k most similar document chunks.
- The retrieved chunks are concatenated as context.
- A prompt is constructed and sent to **Gemini (Google Generative AI)** to generate a final answer.

---

## Usage

### 1. Setup
- Clone this repository.
- Place your PDF files (e.g., `mentalpolicy.pdf`) in the project directory.
- Obtain a Google Gemini API key and set it in the notebook or script.

### 2. Running the System

Open `main.ipynb` and run the cells in order.





