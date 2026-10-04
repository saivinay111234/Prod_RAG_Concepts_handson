# Prod_RAG_Concepts_handson
this repo contains the lessons and handson code to learn RAG lesson by lesson

# 🚀 Retrieval-Augmented Generation (RAG): From Fundamentals to Production

This repository documents my hands-on journey of learning and implementing **Retrieval-Augmented Generation (RAG)** — starting from embedding models and vector databases and progressing toward hybrid retrieval, reranking, evaluation, query transformation, and an end-to-end production-style RAG pipeline.

The goal was not just to understand RAG theoretically, but to implement each major component step by step and understand **why it is needed, how it works, and how it affects retrieval and generation quality**.

---

## 🧠 Topics Covered

### 1. Embedding Models
- What embeddings are and how they represent semantic meaning
- Text-to-vector transformation
- Embedding dimensions
- Cosine similarity
- Comparing embedding models
- Semantic similarity and retrieval

📓 `Embedding Models_lesson1.ipynb`

---

### 2. Vector Databases & Indexing
- Vector storage and retrieval
- Similarity search
- Exact vs Approximate Nearest Neighbor search
- FAISS concepts
- HNSW
- IVF
- Indexing trade-offs
- Recall vs latency

📓 `Vector DBs_lesson2.ipynb`

---

### 3. Sparse vs Dense Retrieval

**Sparse Retrieval**
- TF-IDF
- BM25
- Keyword-based retrieval

**Dense Retrieval**
- Embedding-based semantic search
- Vector similarity
- Semantic matching

Also explored when sparse retrieval performs better than dense retrieval and vice versa.

📓 `Sparse vs Dense Search_lesson3.ipynb`

---

### 4. Hybrid Search

Combined:

`Sparse Retrieval + Dense Retrieval → Hybrid Retrieval`

Covered:
- Keyword + semantic retrieval
- Combining retrieval results
- Ranking strategies
- Reciprocal Rank Fusion concepts
- Improving retrieval coverage

📓 `Hybrid Search_lesson4.ipynb`

---

### 5. Cross-Encoder Reranking

Implemented a two-stage retrieval architecture:

`Retriever → Candidate Documents → Cross-Encoder → Reranked Documents`

Covered:
- Bi-encoder vs cross-encoder
- Candidate retrieval
- Reranking
- Relevance scoring
- Accuracy vs latency trade-offs

📓 `Crossencoders_lesson5.ipynb`

---

### 6. RAG Evaluation

Explored how to evaluate RAG systems beyond simply checking whether an answer "looks correct."

Covered concepts such as:
- Retrieval quality
- Context relevance
- Answer relevance
- Faithfulness
- Context precision
- Context recall
- Grounded generation

📓 `RAG Evaluation_lesson6.ipynb`

---

### 7. Query Transformation + RAGAS

Explored techniques for improving difficult user queries before retrieval.

Covered:
- Query rewriting
- Query expansion
- Query decomposition
- Retrieval improvement
- RAGAS-based evaluation

📓 `Query transformation + RAGAS_lesson7.ipynb`

---

## 🏗️ End-to-End Production RAG

Finally, I combined the concepts into a production-style RAG workflow.

📓 `Prod RAG end-to-end.ipynb`

### Architecture

```text
                         USER QUERY
                              │
                              ▼
                     Query Transformation
                              │
                              ▼
              ┌─────────────────────────────┐
              │        RETRIEVAL            │
              │                             │
              │  Sparse Search ── BM25      │
              │          +                  │
              │  Dense Vector Search        │
              └──────────────┬──────────────┘
                             │
                             ▼
                       Hybrid Search
                             │
                             ▼
                    Candidate Documents
                             │
                             ▼
                    Cross-Encoder Reranker
                             │
                             ▼
                       Top-K Context
                             │
                             ▼
                   ┌───────────────────┐
                   │        LLM        │
                   │ Query + Context   │
                   └─────────┬─────────┘
                             │
                             ▼
                     Grounded Response
                             │
                             ▼
                    RAG Evaluation / RAGAS
```

---

## 📚 Learning Progression

```text
Embeddings
    ↓
Vector Databases
    ↓
Sparse vs Dense Retrieval
    ↓
Hybrid Search
    ↓
Cross-Encoder Reranking
    ↓
RAG Evaluation
    ↓
Query Transformation
    ↓
RAGAS
    ↓
Production RAG Pipeline
```

---

## 💡 Key Takeaways

Building a reliable RAG system involves much more than connecting a vector database to an LLM.

Retrieval quality depends heavily on:

- Embedding quality
- Chunking and indexing strategy
- Sparse vs dense retrieval
- Hybrid retrieval
- Reranking
- Query transformation
- Context selection
- Systematic evaluation

One of my biggest takeaways from this project was that **improving retrieval and evaluation can be just as important as choosing the LLM itself**.

---

## 🛠️ Technologies / Concepts

`Python` • `LLMs` • `Embeddings` • `FAISS` • `Vector Search` • `BM25` • `Hybrid Search` • `Cross-Encoders` • `Reranking` • `RAGAS` • `Retrieval Evaluation` • `Query Transformation`

---

## 🎯 What's Next?

Next, I plan to extend these foundations into:

- Agentic RAG
- Tool calling
- RAG with structured data
- Knowledge graphs / GraphRAG
- RAG observability and monitoring
- Production AI agents
- LLM evaluation pipelines

---

⭐ This repository is part of my hands-on journey toward building **production-ready AI Engineering and Generative AI systems**.
