# 🧠 GenAI & RAG Hands-On Practice (Module 3)

A hands-on, beginner-friendly practice repository covering **Embeddings, Semantic Search, and Retrieval-Augmented Generation (RAG)**.

---

## 📁 Repository Structure

```text
.
├── practice/
│   └── 01_Understanding_Cosine_Similarity.ipynb   # Hands-on cosine similarity & mini-RAG retriever
├── requirements.txt                               # Project dependencies
├── .gitignore                                     # Excludes class notes, venv, and large files
└── README.md                                      # Setup & execution instructions
```

> **Note on Course Lecture Notes:**  
> Proprietary course notebooks (`classes/`) are kept strictly local for study and are ignored by git via `.gitignore`. Only your hands-on practice code and project files are tracked.

---

## 🚀 How to Set Up and Run the Project

### Prerequisites
* Python 3.11 or 3.12
* (Recommended) [`uv`](https://github.com/astral-sh/uv) — an extremely fast Python package manager.

---

### Step 1: Clone and Set Up Virtual Environment

#### Option A: Using `uv` (Recommended - Fastest)
```bash
# 1. Create the virtual environment
uv venv --python 3.12

# 2. Activate the virtual environment
source .venv/bin/activate       # On macOS / Linux
# .venv\Scripts\activate        # On Windows

# 3. Install dependencies
uv pip install -r requirements.txt
```

#### Option B: Using Standard Python
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

### Step 2: Register the Jupyter Kernel

To make sure your editor (VS Code, Cursor, or JupyterLab) uses the virtual environment:

```bash
python -m ipykernel install --user --name "module-3-venv" --display-name "Python (module-3 .venv)"
```

---

### Step 3: Run the Practice Notebooks

1. Open your code editor and navigate to:
   ```text
   practice/01_Understanding_Cosine_Similarity.ipynb
   ```
2. In the top-right corner of the notebook, select the kernel:
   * **`Python (module-3 .venv)`** (or `.venv/bin/python`).
3. Run through the cells step-by-step (`Shift + Enter`).

---

## 🧪 What's Inside `practice/`

### `01_Understanding_Cosine_Similarity.ipynb`
* **Step 1:** Mathematical intuition of Cosine Similarity from scratch (angle vs. vector magnitude).
* **Step 2:** Loading `all-MiniLM-L6-v2` locally using `sentence-transformers` (runs 100% free on your CPU).
* **Step 3:** Vector comparisons using `scikit-learn` (`"dog"` vs `"puppy"` vs `"france"`).
* **Step 4:** The "Apple" disambiguation — seeing Self-Attention distinguish an iPhone device from fresh fruit based on context (*"not turning on"*).
* **Step 5:** Comparing short questions vs. long paragraphs.
* **Step 6:** A complete **10-line Mini-RAG Retriever** that matches user queries to company policies, with an interactive testing cell.
