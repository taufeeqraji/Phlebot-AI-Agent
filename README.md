# 🧪 Phlebot – AI-Powered Medical Information Retrieval Assistant

**Phlebot** is an AI-driven agent that allows healthcare professionals to upload blood test reports as PDFs and query lab results in real time.
It uses **Retrieval-Augmented Generation (RAG)** to interpret lab data, explain test significance, and support clinical decision-making — reducing the need for manual searches through complex medical documents.

## 🚀 Features

* 📄 **PDF Upload Support** – Accepts blood report PDFs and extracts relevant information.
* 🧠 **Contextual Q&A** – Users can ask questions like *“What does high ALT mean?”* and receive precise, medically informed responses.
* 🔍 **RAG Pipeline Integration** – Combines retrieval and generation for accurate context-aware answers.
* ⚙️ **Real-Time Querying** – Responses are generated dynamically using the most relevant sections of the uploaded document.
* 💬 **Conversational Interface** – Built to interact naturally with medical staff in clinical environments.

## 🧱 System Architecture

Phlebot’s pipeline is built using **LangChain** and **OpenAI GPT-4o**, integrating multiple components to deliver intelligent retrieval and reasoning.

### Core Components:

1. **File Loader** – Loads and processes PDF lab reports.
2. **Recursive Character Text Splitter** – Chunks text into overlapping segments for better context preservation.
3. **OpenAI Embeddings (`text-embedding-ada-002`)** – Converts text into semantic vectors.
4. **ChromaDB Vector Store** – Stores embeddings and enables semantic search.
5. **Prompt Template** – Structures the retrieved context and user query for GPT-4o.
6. **OpenAI GPT-4o** – Generates natural language explanations of lab test results.
7. **Parser & Chat Output** – Cleans and formats responses for user readability.

## 🧰 Tech Stack

| Category            | Tools / Frameworks                   |
| ------------------- | ------------------------------------ |
| **LLM**             | OpenAI GPT-4o                        |
| **Framework**       | LangChain                            |
| **Database**        | ChromaDB                             |
| **Embedding Model** | text-embedding-ada-002               |
| **Language**        | Python                               |
| **Pipeline Type**   | Retrieval-Augmented Generation (RAG) |

## ⚙️ Workflow Summary

1. A nurse uploads a **blood test PDF**.
2. The document is parsed and **split into chunks** for efficient processing.
3. Each chunk is embedded and stored in **ChromaDB**.
4. When a user asks a question, the query is embedded and compared semantically against stored vectors.
5. The **most relevant chunks** are retrieved and passed into a structured **prompt template**.
6. **GPT-4o** analyzes the data and returns an accurate, human-readable explanation.

## 🧩 Example Queries

* “Explain what low MCV and MCH mean.”
* “Is this glucose level within the normal range?”
* “What could cause a high ALT reading?”

## 🌍 Real-World Impact

Phlebot was successfully **tested by nurses at Sheikh Shakhbout Medical City (SSMC)** to interpret lab results.
It reduced manual lookup time by **25%**, enabling staff to understand lab parameters faster and provide better patient care.
This project demonstrates how AI can bridge the gap between raw medical data and actionable insight.

## 📈 Future Enhancements

* Integration with **FHIR medical record APIs** for automatic lab uploads.
* Support for **multi-document cross-reference** (e.g., trend analysis across reports).
* Add **confidence scoring** and **medical disclaimer** for compliance.
* Deploy as a **web-based dashboard** or **hospital kiosk app**.
