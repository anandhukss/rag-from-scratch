# 🧠 RAG Engineering & Retrieval Systems from Scratch

A production-oriented engineering repository exploring **Dense Vector Embeddings, Semantic Search, Advanced Document Chunking Strategies, and Retrieval-Augmented Generation (RAG)** systems.

---

## 📁 Repository Structure

```text
.
├── practice/
│   ├── 01_Understanding_Cosine_Similarity.ipynb       # Mathematical vector similarity, polysemy & mini-RAG retriever
│   └── 02_Document_Chunking_Strategies_in_RAG.ipynb   # 7 chunking strategies, tokenizer limits & ChromaDB retrieval
├── requirements.txt                                   # Python dependencies
├── .gitignore                                         # Virtual environments, cache & system files
└── README.md                                          # Architectural overview & setup instructions
```

---

## 🧪 Interactive Notebooks Overview

### 1. [`01_Understanding_Cosine_Similarity.ipynb`](practice/01_Understanding_Cosine_Similarity.ipynb)
* **Mathematical Foundations:** Dot product, L2 vector norms, and cosine similarity calculated from scratch.
* **Local Embedding Inference:** Zero-cost CPU embeddings using `sentence-transformers/all-MiniLM-L6-v2`.
* **Context Disambiguation (Polysemy):** Demonstrating how Self-Attention vectors distinguish between Apple (fruit) vs. Apple (tech device) based on contextual clues.
* **Mini-RAG Retriever:** A complete 10-line semantic search engine matching natural language user queries to internal corporate policies.

### 2. [`02_Document_Chunking_Strategies_in_RAG.ipynb`](practice/02_Document_Chunking_Strategies_in_RAG.ipynb)
* **The 7 Chunking Strategies:** Comprehensive analysis from naive character slicing to cutting-edge semantic splitting.
* **The Mid-Word / Mid-Sentence Split Problem:** Exposing how blind slicing fractures words (`Dig` + `ital`) and destroys embedding vector quality.
* **Sliding Window Mathematics:** Managing chunk overlap and stride ($S = \text{size} - \text{overlap}$) to guarantee boundary continuity.
* **Tokenizer Architecture Comparison:** Benchmarking OpenAI's Byte-Pair Encoding (`cl100k_base`, 100k vocab) vs. MiniLM's WordPiece (30k vocab) on identical corporate text.
* **Structure-Aware Chunking:** Preserving Markdown tables and Python AST function boundaries without breaking header rows.
* **Semantic Chunking from Scratch:** Calculating consecutive sentence cosine distances to automatically trigger breakpoints at topic-shift spikes.
* **ChromaDB Live Retrieval Benchmark:** Demonstrating how optimal chunking reduces vector distance from `0.8366` to `0.5795` and eliminates LLM context pollution.

---

## 🚀 Getting Started

### Prerequisites
* Python 3.11 or 3.12
* Recommended: [`uv`](https://github.com/astral-sh/uv) (fast Python package manager)

---

### Step 1: Clone and Set Up Virtual Environment

#### Option A: Using `uv` (Recommended)
```bash
# 1. Create virtual environment
uv venv --python 3.12

# 2. Activate virtual environment
source .venv/bin/activate       # On macOS / Linux
# .venv\Scripts\activate        # On Windows

# 3. Install dependencies
uv pip install -r requirements.txt
```

#### Option B: Using Standard Python `venv`
```bash
# 1. Create virtual environment
python3 -m venv .venv

# 2. Activate virtual environment
source .venv/bin/activate       # On macOS / Linux
# .venv\Scripts\activate        # On Windows

# 3. Install dependencies
pip install -r requirements.txt
```

---

### Step 2: Register Jupyter Kernel

To make the environment available in VS Code, Cursor, or JupyterLab:

```bash
python -m ipykernel install --user --name "rag-from-scratch-venv" --display-name "Python (rag-from-scratch)"
```

---

### Step 3: Run the Notebooks

1. Open your code editor and select a notebook from `practice/`.
2. In the top-right corner, select the kernel:
   * **`Python (rag-from-scratch)`** (pointing to `.venv/bin/python`).
3. Run through the cells interactively (`Shift + Enter`).
