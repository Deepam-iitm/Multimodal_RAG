## Multi-Modal RAG: 📊
A powerful Retrieval-Augmented Generation (RAG) pipeline designed to understand both textual data and visual charts from PDF documents. 
This project uses OpenAI's CLIP for unified cross-modal embeddings and Google's Gemini 3 Flash for intelligent synthesis.

## 🌟 Key Features
* Dual-Modality Retrieval: Uses CLIP to embed both text chunks and images/charts into the same vector space.
* Intelligent PDF Parsing: Automatically extracts text and captures visual "snapshots" of pages containing charts or graphics that traditional parsers miss.
* Gemini 3 Flash Integration: Leverages the massive context window and native multi-modal capabilities of Gemini 3 to answer questions based on retrieved visuals.

## 🏗️ Architecture
* Ingestion: PDF pages are parsed for text and converted into high-resolution images.
* Embedding: Text and Images are processed via CLIP (ViT-B/32) to generate 512-dimension vectors.
* Storage: Vectors are indexed using FAISS for lightning-fast similarity searching.
* Retrieval: User queries are embedded via CLIP to find the most relevant text AND image context.
* Generation: Retrieved context (Text + Base64 Images) is sent to Gemini 3 Flash to generate a final, grounded answer.

## 🛠️ Tech Stack
* LLM: Google Gemini 3 Flash
* Embedding Model: OpenAI CLIP
* Orchestration: LangChain
* Vector DB: FAISS
* PDF Processing: PyMuPDF (fitz)

🚀 Getting Started
1. Clone the repository
   * `git clone https://github.com/Deepam-iitm/Multimodal_RAG.git`
2. Create a virtual environment
   * `python -m venv venv`
4. Install dependencies
   * `pip install -r requirements.txt`
5. Create a .env file and set up your API Key
6. Start running the notebook.
