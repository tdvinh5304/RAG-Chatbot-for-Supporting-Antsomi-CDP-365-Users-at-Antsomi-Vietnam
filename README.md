# RAG-Chatbot-for-Supporting-Antsomi-CDP-365-Users-at-Antsomi-Vietnam
## Project Overview

This project focuses on building a **Retrieval-Augmented Generation (RAG) Chatbot** to support users in exploring, understanding, and using the **Antsomi CDP 365** platform.

The chatbot is designed to answer user questions in **natural language** by retrieving verified internal documentation and generating accurate, context-aware responses. The goal is to reduce repetitive support requests, improve user experience, and ensure consistent access to up-to-date product knowledge.

This project was developed during an **internship at Antsomi Vietnam** as part of a graduation internship report.


## Objectives

* Support CDP 365 users in learning and operating complex system features
* Reduce workload for technical support and product teams
* Ensure answers are **accurate, traceable, and based on verified documents**
* Enable easy updates when documentation or product features change


## Why RAG?

Traditional LLM-based chatbots may:

* Generate hallucinated or outdated answers
* Be difficult to control in enterprise environments

The **RAG architecture** solves this by:

* Retrieving answers only from approved internal documents
* Allowing real-time knowledge updates without model retraining
* Providing higher accuracy and better content control

This makes RAG especially suitable for **enterprise software support** like CDP 365.


## System Architecture

The system follows a multi-stage RAG pipeline:

1. **Document Ingestion**

   * Crawl CDP 365 documentation from GitBook
   * Clean, chunk, and normalize content
   * Generate vector embeddings

2. **Knowledge Storage**

   * Store embeddings in **PostgreSQL + pgvector (Supabase)**
   * Attach metadata (title, URL, module, timestamp)

3. **Query Processing**

   * User submits a natural-language question
   * Query is rewritten and embedded (HyDE supported)
   * Semantic search retrieves relevant document chunks
   * Results are re-ranked for relevance

4. **Answer Generation**

   * LLM generates a final answer grounded in retrieved content
   * Guardrails applied to reduce hallucination
   * Chat history stored for contextual continuity


## Tech Stack

| Category         | Technology                           |
| ---------------- | ------------------------------------ |
| Orchestration    | **n8n**                              |
| LLM              | **OpenAI GPT-4.1-mini**              |
| Vector DB        | **Supabase (PostgreSQL + pgvector)** |
| Reranking        | **Cohere Rerank**                    |
| Data Crawling    | **Firecrawl**                        |
| Backend Logic    | **JavaScript (n8n custom nodes)**    |
| Knowledge Source | **GitBook**                          |


## Key Features

* Natural language question answering
* Semantic search over internal documentation
* Metadata-based filtering and ranking
* Multi-turn conversation memory
* Easy document updates without retraining
* AI-friendly documentation standards


## Functional Requirements

* Accept natural language queries from users
* Retrieve relevant content from verified documents
* Generate clear, accurate, context-aware answers
* Store conversation history per session
* Allow admins to update the knowledge base


## Non-Functional Requirements

* Response time under **5 seconds**
* Secure access to internal documentation
* Scalable vector storage
* Easy maintenance and pipeline extensibility


## Testing & Evaluation

* Real user questions were used for validation
* Incorrect or unclear answers were logged
* Documentation and metadata were refined iteratively
* Retrieval accuracy and relevance were improved through reranking and chunk tuning


## Results

* Chatbot successfully answered CDP 365 usage questions
* Reduced dependency on manual support
* Documentation quality improved through AI-feedback loops
* System ready for internal demo and future integration


## Future Improvements

* Role-based access control for sensitive documents
* Analytics dashboard for chatbot performance
* Deeper integration with CDP 365 UI


## Author

**Tiêu Đăng Vinh**
Business Analyst Intern – Antsomi Vietnam
Major: Digital Business & Artificial Intelligence
