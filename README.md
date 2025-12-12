# Norma — RAG-based IT Compliance Assistant

**Norma** is an intelligent assistant for **IT compliance and cybersecurity standards**.
Using *Retrieval-Augmented Generation (RAG)* on Azure, Norma answers questions from PDF standards and policy documents to support **compliance checks, audits, and gap analysis**.

---

## 🚀 Overview

Norma helps auditors, security engineers, and compliance teams overcome complex documentation challenges by:

* extracting relevant information from regulatory and standards PDFs
* retrieving the most pertinent sections via semantic search
* generating *contextual and grounded responses* using GPT

This repository provides a production-ready architecture combining **Azure AI Foundry**, **Phi-4**, and a local **Python → FastAPI backend**.

---

## 🔎 Features

* 📄 **Document Ingestion** — Parse and index PDF standards
* 🧠 **Semantic Retrieval** — Fast vector search for relevant content
* 💬 **Natural Language Answers** — GPT responses grounded in retrieved text
* 📊 **Audit & Gap Analysis Support** — Helps identify compliance gaps
* ⚙️ **Secure Local API** — FastAPI server running locally

---

## 🧠 Architecture

```
[PDF Standards] → Ingestion & Chunking → Embedding Store
          ↓
Semantic Vector Search (Azure / Local index)
          ↓
   Retrieved Context + User Query
          ↓
Azure AI Foundry (Phi-4) → Contextual GPT Response
          ↓
   FastAPI Backend → API / UI
```

**Tech stack:**

* ☁️ Azure AI Foundry (Phi-4 as LLM provider)
* 🐍 Python backend (FastAPI)
* 📑 PDF parsing + semantic indexing
* 🔍 Vector search (Azure Search)

---

## 📌 Example Usage

**Example questions Norma can answer:**

* “Which ISO 27001 controls cover access management?”
* “What gaps exist between our procedures and NIST CSF requirements?”
* “Does this policy meet GDPR compliance criteria?”

Answers include **relevant excerpts from the source PDFs**, providing context and traceability.

---

## 💻 Local Setup

### Prerequisites

* Python 3.10+
* Azure account with AI Foundry access
* Required environment variables set (Azure credentials, endpoints)

### Installation

```bash
git clone https://github.com/VanCrypt/norma-rag-it-compliance.git
cd norma-rag-it-compliance
pip install -r requirements.txt
```

### Run Locally

```bash
uvicorn app.main:app --reload
```

Default API endpoint:

```
http://localhost:8000
```

---

## 🛠️ Usage Example

**Query the API:**

```bash
curl -X POST http://localhost:8000/query \
     -H "Content-Type: application/json" \
     -d '{"question": "What are ISO 27001 Annex A controls for encryption?"}'
```

---






