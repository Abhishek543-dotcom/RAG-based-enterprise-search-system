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
