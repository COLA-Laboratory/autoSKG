# 🌿autoSKG

**Automated Scientific Knowledge Graph Construction Pipeline for [PlantScience.ai](https://plantscience.ai)**  

autoSKG is the backend engine that powers **PlantScience.ai**, an LLM-powered virtual scientist for plant biology.  
It automatically extracts, structures, and updates scientific knowledge from research papers to build a **domain-specific, continuously evolving knowledge graph (KG)**.  

---

## 🚀 Features
- **Automated Knowledge Extraction** – Converts unstructured scientific literature (PDFs) into structured entities and relationships.  
- **PlantScience.ai Integration** – Forms the core KG engine supporting the PlantScience.ai virtual scientist.  
- **Continuous Updates** – Supports incremental updates by detecting and integrating new knowledge from added PDFs.  
- **Traceable Knowledge** – Every entity and relationship in the graph is linked to its original publication source.  
- **Dockerized Pipeline** – Fully containerized for reproducible and scalable deployment.  

---

## 📦Prerequisites
 - [Docker](https://www.docker.com/products/docker-desktop)
 - [Docker Compose](https://docs.docker.com/compose/)
 - An [OpenAI API key](https://platform.openai.com/account/api-keys)  
 - *(Optional)* A [Docker Hub](https://hub.docker.com) account if pushing/pulling images  

 > 💡 Place your PDF documents in the `input_pdfs/` folder before running.

---

## 🐳Run with Docker Compose
### 1.Clone the repository

```bash
git clone https://github.com/COLA-Laboratory/autoSKG.git
cd autoSKG
```

### 2. Add input PDFs
Place your PDF files inside the ``input_pdfs/`` directory:
```
input_pdfs/
├── paper1.pdf
├── paper2.pdf
```

### 3. Set your OpenAI API Key

The `autoSKG` requires an OpenAI API key for GPT-based processing.

1. Open the `.env` file (create one if it doesn't exist)
2. Add the following line:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

### 4. Start the pipeline
Run the following command to start all services:

```
docker compose up --build
```

---

## 📂 Output
After execution, results will be saved to:
  - kg_project/output/
  - kg_project/input/
  - kg_project/cache/

---

## 🐙 Knowledge Graph Update
1. Add PDF files inside the ``input_pdfs/`` directory
2. Start the pipeline
Run the following command to start all services:

```
# Add new files to input_pdfs/
docker compose up --build
```
---

## 🧹 Clean Up
To stop and remove containers:

```
docker compose down
```
---

## 🌱 About PlantScience.ai

**[PlantScience.ai](https://plantscience.ai)** is a **virtual scientist for plant biology**, combining large language models with the domain-specific knowledge graph built by autoSKG.
It provides accurate, citation-grounded answers and interactive graph visualizations of biological concepts — supporting next-generation scientific discovery.
