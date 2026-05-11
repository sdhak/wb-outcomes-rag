# Development Policy Intelligence 

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

## Key Findings
Sample outputs from querying the document corpus:

**Q: What were the key performance indicators and were targets achieved?**
> Based on the provided World Bank project documents, the key 
> performance indicators for the India ISSNIP program:
> - District resource groups trained: Target 100%, Achieved 100%
> - Anganwadi Workers trained on ICT: Target 76.94%, Achieved 76.94%
> - AWCs reporting nutrition indicators via ICT: Target 60%, Achieved 60%
>
> For Nepal Higher Education Reforms Project:
> - Publications in refereed journals: Target 85, Achieved 140 
>   (overachieved by 164.7%)

**Q: What lessons were learned from project implementation?**
> Key lessons included the importance of strong leadership during 
> disasters, decentralized decision-making accelerating implementation, 
> regular supervision every six months identifying bottlenecks early, 
> and the value of project extensions in ensuring objectives are met.

**Q: What is the overall outcome rating?**
> The overall outcome rating is Substantial, with High relevance 
> rating continuing focus on reforms and capacity building.

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
4. Download ICR documents from openknowledge.worldbank.org 
   (see data/README.md for direct links)
5. Run notebooks/wb_outcomes_rag.ipynb
