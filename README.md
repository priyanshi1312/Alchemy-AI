# Alchemy

Alchemy is a Retrieval-Augmented Generation (RAG) based AI PDF Knowledge Assistant that enables users to interact with PDF documents using natural language. The application leverages Spring Boot, Spring AI, Ollama, Qdrant, and Redis to provide context-aware question answering and document summarization through semantic search.

## Features

- Upload and manage multiple PDF documents
- Retrieval-Augmented Generation (RAG)
- AI-powered question answering
- Context-aware document summarization
- Semantic search using vector embeddings
- Local LLM inference with Ollama
- High-performance vector search with Qdrant
- Redis-based caching for improved response times
- RESTful API built with Spring Boot

---

## Technology Stack

| Category | Technologies |
|----------|--------------|
| Language | Java 21 |
| Backend | Spring Boot, Spring AI |
| AI | Ollama |
| Vector Database | Qdrant |
| Cache | Redis |
| Document Processing | PDF Parsing, Text Chunking, Embedding Generation |
| Build Tool | Maven |
| API Testing | Postman |
| Version Control | Git, GitHub |

---

## System Architecture

```
                User
                  │
                  ▼
          Spring Boot REST API
                  │
                  ▼
             Spring AI
                  │
      ┌───────────┴───────────┐
      ▼                       ▼
 PDF Processing          Redis Cache
      │                       │
      ▼                       │
 Text Chunking                │
      │                       │
      ▼                       │
Embedding Generation          │
      │                       │
      ▼                       │
   Qdrant Vector Store ◄──────┘
      │
      ▼
Relevant Context Retrieval
      │
      ▼
  Ollama (LLM)
      │
      ▼
 Generated Response
```

---

## How It Works

1. Users upload one or more PDF documents.
2. Documents are parsed and divided into semantic chunks.
3. Embeddings are generated for each chunk.
4. Embeddings are stored in Qdrant for semantic retrieval.
5. User queries are converted into embeddings.
6. Relevant document chunks are retrieved from Qdrant.
7. Retrieved context is combined with the user query.
8. Spring AI sends the prompt to Ollama.
9. Redis caches frequently accessed responses to reduce latency.
10. The generated response is returned to the user.

---

## Project Structure

```
src
├── controller
├── service
├── config
├── model
├── repository
├── dto
└── resources
```



## Screenshots

<img width="1600" height="795" alt="WhatsApp Image 2026-07-28 at 11 17 40 AM" src="https://github.com/user-attachments/assets/5336c226-d0b3-4843-82ba-3bb9a2d11c30" />




## Future Improvements

- Multi-model support
- Cloud deployment
- Source citations
