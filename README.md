# 🌿autoSKG

This project extracts structured knowledge graph from PDF documents.

## 📦Prerequisites
 - [Docker](https://www.docker.com/products/docker-desktop)
 - [Docker Compose](https://docs.docker.com/compose/)
 - A Docker Hub account (if pushing/pulling images)
 - Your PDFs should be placed in the ``input_pdfs/`` folder

## 🐳Run with Docker Compose
1.Clone the repository

```bash
git clone https://github.com/COLA-Laboratory/autoSKG.git
cd autoSKG
```

2. Add input PDFs
Place your PDF files inside the ``input_pdfs/`` directory:
```
input_pdfs/
├── paper1.pdf
├── paper2.pdf
```

3. Set your OpenAI API Key

The `autoSKG` requires an OpenAI API key for GPT-based processing.

1. Open the `.env` file (create one if it doesn't exist)
2. Add the following line:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

4. Start the pipeline
Run the following command to start all services:

```
docker-compose up --build
```

### 📂 Output
After execution, results will be saved to:
  - kg_project/output/
  - kg_project/input/
  - kg_project/cache/

## 🐙 Knowledge Graph Update
1. Add PDF files inside the ``input_pdfs/`` directory
2. Start the pipeline
Run the following command to start all services:

```
docker compose up --build
```

## 🧹 Clean Up
To stop and remove containers:

```
docker compose down
```
