# wb-outcomes-rag

# World Bank Project Outcomes Explorer

### A RAG Application for Development Outcomes Analysis

## Overview
This project builds a Retrieval-Augmented Generation (RAG) 
application that enables natural language querying of World Bank 
Implementation Completion Reports (ICRs) across South Asia.

Users can ask questions like:
- "What were the key performance indicators for Nepal education projects?"
- "What is the overall outcome rating of the Bangladesh HEAT project?"
- "What lessons were learned from project implementation?"

The tool surfaces structured outcome data, KPI achievements, and 
lessons learned directly from official World Bank project documents.

## Background
The World Bank and other development institutions produce hundreds 
of project completion reports annually, documenting outcomes, 
performance indicators, and lessons learned across sectors and 
regions. This institutional knowledge is valuable but difficult 
to navigate at scale.

This project explores how RAG architecture can make dense policy 
documents queryable and accessible — enabling faster synthesis of 
development evidence across a large document corpus.

## Technical Stack
- **LangChain** — RAG pipeline orchestration
- **ChromaDB** — Local vector store for document embeddings
- **HuggingFace** — Sentence embeddings (all-MiniLM-L6-v2)
- **Groq (Llama 3.1)** — LLM for answer generation
- **PyPDF** — PDF document loading

## Documents Used
World Bank Implementation Completion Reports (ICRs) — publicly 
available via the World Bank Open Knowledge Repository 
(openknowledge.worldbank.org):
- Nepal Basic and Primary Education Project II
- Nepal Higher Education Reforms Project
- Nepal Engineering Education Project
- Nepal Health Sector Project (ICR00005984)
- Bangladesh Higher Education Acceleration & Transformation (HEAT)

## Setup
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Add your Groq API key (free at console.groq.com):
```python
os.environ["GROQ_API_KEY"] = "your_key_here"
