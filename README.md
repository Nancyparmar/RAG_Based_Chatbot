# RAG-Based Chatbot using Phi-2

A **Retrieval-Augmented Generation (RAG)** chatbot built with LangChain and FAISS that answers questions strictly from a provided document — and honestly replies **"I don't know"** for anything outside it.

---

## What it does

Most LLMs hallucinate — they make up answers confidently. This chatbot solves that by:
1. Loading your document and splitting it into chunks
2. Converting chunks into vector embeddings using Sentence Transformers
3. When a question is asked, retrieving only the most relevant chunks
4. Passing those chunks + the question to Phi-2 to generate a grounded answer

If the answer isn't in the document, it says so.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| LangChain | RAG pipeline & text splitting |
| FAISS | Vector similarity search |
| Phi-2 (Hugging Face) | Language model for answer generation |
| Sentence Transformers | Text embeddings |
| Jupyter Notebook | Development environment |

---

## Project Structure

```
RAG_Based_Chatbot/
├── RAG_Based_chatbot.ipynb   # Main notebook
├── DSML.txt                  # Sample document used for Q&A
├── requirements.txt          # Dependencies
└── README.md
```

---

## Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/Nancyparmar/RAG_Based_Chatbot.git
cd RAG_Based_Chatbot
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebook
Open `RAG_Based_chatbot.ipynb` in Jupyter and run all cells.

You can replace `DSML.txt` with any `.txt` document of your choice.

---

## How it works (simplified)

```
Your Document
     ↓
Text Splitting (chunks)
     ↓
Sentence Transformer Embeddings
     ↓
FAISS Vector Store
     ↓
User Question → Similarity Search → Top Relevant Chunks
                                          ↓
                                    Phi-2 LLM → Answer
```

---

## Sample Output

```
Question: What is supervised learning?
Answer: Supervised learning is a type of machine learning where the model 
is trained on labeled data, meaning each training example has an input 
and a corresponding correct output...

Question: What is the capital of France?
Answer: I don't know. (not in the document)
```

---

## Requirements

```
langchain
faiss-cpu
sentence-transformers
transformers
torch
```

---

## Future Improvements

- [ ] Support PDF and web URL as input sources
- [ ] Add Streamlit UI for easier interaction
- [ ] Support multiple documents simultaneously
- [ ] Swap Phi-2 with Llama-2 or Mistral for better accuracy

---

## Author

**Nancy Parmar** — [GitHub](https://github.com/Nancyparmar) · [LinkedIn](https://www.linkedin.com/in/nancy-parmar/)

> Built during Data Science Internship at C9 Lab, Indore
