
# Grok Knowledge Base Interaction and Vector Database Integration

[Open this notebook in Google Colab](https://colab.research.google.com/github/aifunz/kb-grok/blob/main/Grok_KB_Folder.ipynb)

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

## How to Use

1. Open the notebook using the [Google Colab link](https://colab.research.google.com/github/aifunz/kb-grok/blob/main/Grok_KB_Folder.ipynb).
2. Follow the instructions in the notebook to mount Google Drive and set up the environment.
3. Configure your `.env` file with the required variables:
   ```plaintext
   # Environment settings for kb-grok

   SAVE_DIR=/content/drive/MyDrive/vector_db
   VECTOR_DB_DIR=/content/drive/MyDrive/vector_db
   VECTORS_JOBLIB=vectors.joblib
   VECTORIZER_JOBLIB=vectorizer.joblib
   HASHES_JOBLIB=file_hashes.joblib

   FOLDER_ID=
   GROK_API_KEY=
   GROK_MODEL=grok-2-latest
   GROK_TEMP=0
   ```

4. Run the notebook cells to initialize and use the chat interface.

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](https://www.apache.org/licenses/LICENSE-2.0) file for details.
