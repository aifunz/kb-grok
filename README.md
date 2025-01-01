
# Grok Knowledge Base Interaction and Vector Database Integration

This project provides an enhanced chat interface with integrated support for a FAISS-based vector database. The application enables querying and retrieving information from a knowledge base, using FAISS for similarity search and context retrieval.

## Features

- **FAISS Vector Database Integration**: 
  - Store, manage, and retrieve vector representations of documents.
  - Efficient similarity search with k-nearest neighbors.
  
- **Chat Interface**: 
  - Allows user interaction with the knowledge base.
  - Contextual responses utilizing vector similarity.
  
- **Logging and Metrics**:
  - Logs chat interactions and stores them in markdown format.
  - Tracks metrics for vector searches, including search time, success rate, and average similarity.

- **Google Drive Integration**:
  - Enables saving and loading of vector databases and chat logs directly from Google Drive.

## Components

1. **VectorDB**:
   - Manages the FAISS vector database.
   - Supports vector addition, retrieval, and similarity search.
   
2. **ChatLogger**:
   - Handles logging of interactions for session tracking and debugging.
   
3. **VectorSearchMetrics**:
   - Tracks and reports statistics about vector search operations.

4. **ChatInterface**:
   - User-facing component for querying the knowledge base.
   - Integrates with FAISS for context-aware responses.

## How to Use with Google Colab

1. **Prerequisites**:
   - A Google account with access to Google Colab and Google Drive.
   - Python 3.x installed on the Colab instance.
   - Libraries: `faiss`, `numpy`, `requests`, `ipywidgets`, `google.colab`.

2. **Setup**:
   - **Google Drive Integration**:
     - Mount Google Drive in your Colab notebook:
       ```python
       from google.colab import drive
       drive.mount('/content/drive')
       ```
     - Ensure your vector database files are saved in the appropriate directory (e.g., `/content/drive/MyDrive/vector_db`).

   - **Configure Environment Variables**:
     - Rename the `_env` file to `.env` and save it in `My Drive/Colab Notebooks`.
     - The `.env` file attributes should include:
       ```plaintext
       # Environment settings used by https://github.com/aifunz/kb-grok
       # Rename this .env and save it to My Drive/Colab Notebooks

       # Vector path and file names
       SAVE_DIR=/content/drive/MyDrive/vector_db
       VECTOR_DB_DIR=/content/drive/MyDrive/vector_db
       VECTORS_JOBLIB=vectors.joblib
       VECTORIZER_JOBLIB=vectorizer.joblib
       HASHES_JOBLIB=file_hashes.joblib

       # Google Drive folder ID that will be vectorized for the knowledge base
       FOLDER_ID=

       # Grok settings - get an API key here https://console.x.ai/
       GROK_API_KEY=
       GROK_MODEL=grok-2-latest

       # Temperature determines the creativity of the response
       GROK_TEMP=0
       ```

   - **Set Up Variables in Colab**:
     - Load the `.env` file in your Colab environment:
       ```python
       import os
       from dotenv import load_dotenv
       load_dotenv('/content/drive/MyDrive/Colab Notebooks/.env')
       ```

3. **Execution**:
   - Run the notebook to initialize the chat interface.
   - Use the chat interface to query the knowledge base.

4. **Knowledge Base Folder**:
   - Specify the Google Drive folder ID to vectorize documents in the `.env` file under `FOLDER_ID`.

## Key Functions

- **`find_similar_documents(query_vector, k)`**:
  - Finds the `k` most similar vectors to the query.
  
- **`get_document_vector(file_id)`**:
  - Retrieves the vector representation of a specific document.
  
- **`log_interaction(query, response)`**:
  - Logs a query-response pair for tracking and reference.

- **`send_message(query)`**:
  - Processes a user query, retrieves relevant context, and generates a response.

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](https://www.apache.org/licenses/LICENSE-2.0) file for details.
