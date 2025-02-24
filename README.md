# Retrieval-Augmented Generation (RAG) Pipeline with FAISS and Azure OpenAI

This repository contains a pipeline for web scraping, document indexing, and semantic search using FAISS and Azure OpenAI. It integrates web crawling with Tavily, text embedding using Sentence Transformers, and retrieval-based summarization using GPT.

**Features**

1. Web scraping using Tavily API

2. Chunking text using LangChain's RecursiveCharacterTextSplitter

3. Embedding using sentence-transformers

4. Indexing and similarity search using FAISS

5. Retrieval-augmented generation (RAG) using Azure OpenAI

**Installation**
**Clone the repository:**

**Create a virtual environment and activate it:**
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

**Install dependencies:**
pip install -r requirements.txt

**Configuration**
**create a .env file:**
TAVILY_API_KEY=your-tavily-api-key
AZURE_OPENAI_API_KEY=your-azure-api-key
AZURE_OPENAI_ENDPOINT=your-azure-endpoint

**Running the Scraper**
python search_crawl.py

Reads queries from queries.txt
Fetches search results using Tavily API
Extracts raw content from search results

**Indexing Documents**

To generate embeddings and create a FAISS index:
python index_documents.py

Loads raw content
Splits text into smaller chunks
Generates embeddings using SentenceTransformer
Stores vectors in FAISS index

**Running a Search Query**

To perform similarity search and retrieve results:
python search_rag.py --query "What is the net worth of Neymar?"

Embeds the query
Searches the FAISS index
Retrieves relevant documents
Uses GPT-4 to summarize search results



