
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

## How to Run

1. **Prerequisites**:
   - Python 3.x.
   - Libraries: `faiss`, `numpy`, `requests`, `ipywidgets`, `google.colab`.

2. **Setup**:
   - Place your vector database files (`faiss_index.index`, `metadata.json`) in the specified `save_dir`.
   - Modify the configuration variables (`SAVE_DIR`, `MODEL`, `TEMP`) as required.

3. **Execution**:
   - Run the notebook to initialize the chat interface.
   - Interact with the knowledge base using the chat input.

4. **Google Drive Integration**:
   - Ensure Google Drive is mounted if using it to store vector database files.

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
