# Aurora Stay Q&A

A Retrieval-Augmented Generation (RAG) assistant that answers guest questions about AuroraStay hotel policies, such as booking and cancellation, refunds and charges, guest conduct and accessibility, and room and property information.

## Structure

- `Full_Code_Notebook.ipynb`: development notebook covering document ingestion, indexing, RAG pipeline, and evaluation.
- `Data/`: source policy PDFs plus `evaluation.csv` and `test.csv`.
- `backend_files/`: Flask API with a FAISS vector store and RAG utilities (`app.py`, `rag_utils.py`, `Dockerfile`).
- `frontend_files/`: Streamlit chat UI (`app.py`, `Dockerfile`).

## Setup

1. Install dependencies: `pip install -r backend_files/requirements.txt` (and `frontend_files/requirements.txt`).
2. Create a `config.json` with your OpenAI credentials (it is git-ignored):
   ```json
   {"OPENAI_API_KEY": "...", "OPENAI_API_BASE": "https://api.openai.com/v1"}
   ```
3. Start the backend: `cd backend_files && python app.py`
4. Start the frontend: `cd frontend_files && streamlit run app.py`

Both services also include Dockerfiles for containerized deployment.
