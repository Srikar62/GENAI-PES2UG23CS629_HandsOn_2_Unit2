## Project Summary

This repository contains three Jupyter notebooks that walk through progressively richer GenAI exercises:

- **`BASICprompt.ipynb`** – foundational prompt design patterns and structured prompt formatting.
- **`Advanced_prompting.ipynb`** – advanced prompting techniques, including step-by-step reasoning approaches.
- **`LANGCHAIN.ipynb`** – LangChain-based usage with Google Generative AI models, including parameter tuning (such as temperature).

Together, they form a compact hands-on learning path for students and beginners who want to understand practical LLM prompting from basic to intermediate depth.

---

## Features

- Notebook-first learning workflow for quick experimentation.
- Examples of both **basic** and **advanced** prompt-writing styles.
- Demonstrates structured prompts for more controlled outputs.
- LangChain integration with Google Generative AI.
- Simple setup using environment variables (`.env`) for API credentials.

---

## How to Install

### 1) Clone the repository

```bash
git clone https://github.com/Srikar62/GENAI-PES2UG23CS629_HandsOn_2_Unit2.git
cd GENAI-PES2UG23CS629_HandsOn_2_Unit2
```

### 2) Create and activate a virtual environment (recommended)

```bash
python -m venv .venv
source .venv/bin/activate        # Linux/macOS
# .venv\Scripts\activate          # Windows (PowerShell)
```

### 3) Install dependencies

You can install dependencies used in the notebooks directly:

```bash
pip install --upgrade python-dotenv langchain langchain-google-genai jupyter
```

### 4) Configure environment variables

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_google_genai_api_key_here
```

---

## How to Run

### Option A: Run with Jupyter Notebook

```bash
jupyter notebook
```

Then open and execute cells in:
- `BASICprompt.ipynb`
- `Advanced_prompting.ipynb`
- `LANGCHAIN.ipynb`

### Option B: Run with JupyterLab

```bash
jupyter lab
```

---

## Example Usage

A typical flow in this repository is:

1. Load API keys from `.env`.
2. Initialize a language model via LangChain.
3. Send a prompt and inspect output.
4. Refine prompt structure or model parameters (e.g., temperature) and compare responses.

Example snippet:

```python
from dotenv import load_dotenv
from langchain_google_genai import ChatGoogleGenerativeAI

load_dotenv()

llm = ChatGoogleGenerativeAI(model="gemini-1.5-flash", temperature=0.7)
response = llm.invoke("Define the word 'idea' in one sentence.")
print(response.content)
