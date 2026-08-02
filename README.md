# 🍽️ Interactive Food Search & RAG Chatbot System

A Python project demonstrating three progressively advanced approaches to building AI-powered search and recommendation systems using **vector embeddings**, **semantic similarity search**, and **Retrieval-Augmented Generation (RAG)**.

Built on a dataset of food items (ingredients, nutrition, cuisine, cooking methods) as a working example of how vector databases and LLMs combine to power modern recommendation and conversational AI systems.

---

## 🚀 What This Project Demonstrates

| System | What It Shows |
|---|---|
| **Interactive CLI Search** | Real-time semantic search with a conversational command-line interface |
| **Advanced Filtered Search** | Combining vector similarity with structured metadata filters (cuisine, calories, ingredients) |
| **RAG Chatbot** | Retrieval-Augmented Generation — grounding an LLM's responses in retrieved data instead of letting it hallucinate |

Together, these show the same underlying data pipeline solved three different ways — a common real-world engineering decision: *when do you need simple search vs. filtered search vs. a full conversational AI layer?*

---

## 🛠️ Tech Stack

- **Python 3**
- **ChromaDB** — vector database for storing and querying embeddings
- **Sentence-Transformers** (`all-MiniLM-L6-v2`) — converts text into semantic embeddings
- **IBM watsonx.ai** — LLM integration for natural language response generation
- **NumPy** — similarity score calculations
- Pure CLI — no web framework dependency, focused on core logic

---

## 📁 Project Structure

```
Interactive-Food-Search-and-RAG-Chatbot-System/
├── src/
│   ├── shared_functions.py       # Core reusable logic: data loading, embedding, search
│   ├── interactive_search.py     # CLI chatbot for basic semantic search
│   ├── advanced_search.py        # Search with cuisine/calorie/ingredient filtering
│   ├── enhanced_rag_chatbot.py   # Full RAG pipeline: retrieval + LLM-generated responses
│   └── system_comparison.py      # Side-by-side benchmarking of all three systems
├── exercises/
│   ├── calorie_checker.py               # Budget-aware food search tool
│   ├── result_limiter.py                # Explores how result count affects search quality
│   └── interactive_search_with_history.py  # Adds session search-history tracking
├── .gitignore
└── README.md
```

---

## ⚙️ Core Concepts Implemented

- **Embedding generation** from structured JSON records (name, description, ingredients, nutrition, taste profile) into dense vector representations
- **Cosine similarity search** via ChromaDB collections
- **Metadata filtering** (`$and`, `$lte` style query operators) layered on top of vector search
- **RAG architecture**: retrieving top-k relevant context → injecting it into an LLM prompt → generating a grounded, conversational response
- **Fallback handling** for when the LLM is unavailable or context is insufficient
- **CLI UX design**: command parsing, help menus, interactive loops, error handling

---

## 🧪 Getting Started

```bash
# 1. Clone the repo
git clone https://github.com/Vivek6566/Interactive-Food-Search-and-RAG-Chatbot-System.git
cd Interactive-Food-Search-and-RAG-Chatbot-System

# 2. Install dependencies
pip install numpy scipy chromadb sentence-transformers ibm-watsonx-ai

# 3. Add the dataset (FoodDataSet.json) to the project root
# (not committed to the repo — see .gitignore)

# 4. Run any of the systems
python src/interactive_search.py
python src/advanced_search.py
python src/enhanced_rag_chatbot.py
python src/system_comparison.py
```

> **Note:** `enhanced_rag_chatbot.py` requires IBM watsonx.ai credentials. Set these as environment variables rather than hardcoding them.

---

## 💡 Why This Project

This project was built to practice and demonstrate:
- Designing modular, reusable Python code across multiple applications (`shared_functions.py` as a shared core)
- Working hands-on with vector databases and embedding models — foundational to modern AI/ML applications (semantic search, recommendation engines, RAG systems)
- Understanding the tradeoffs between simple similarity search, filtered search, and full conversational AI — a practical architecture decision in real systems
- Building usable CLI tools with thoughtful UX (help menus, error handling, interactive flows) without relying on a web framework

---

## 📄 License

This project was completed as part of an IBM Skills Network guided lab and is shared here for portfolio and learning purposes.
