# Bug Whisperer: An Agentic Self-Healing Codebase

## Overview
This repository implements a workflow-based error detection and correction system that combines LangGraph, LLM capabilities, and vector database technology to detect runtime errors, generate fixes, and maintain a memory of bug patterns. The system processes function definitions and runtime arguments through a graph-based workflow, maintaining a hierarchical error management system enriched by vector-based similarity search.

---

## Motivation
### Key Drivers Behind This Implementation:
1. **Automated Error Resolution**
   - Reduces manual debugging effort.
   - Streamlines error correction using LLM-generated, context-aware fixes.

2. **Pattern-Based Learning**
   - Leverages vector databases for bug pattern recognition.
   - Informs future error resolution using past fixes.
   - Enhances fix relevance with semantic search capabilities.

3. **Structured Bug Knowledge**
   - Captures semantic relationships between errors using vector embeddings.
   - Implements hierarchical error categorization through vector spaces.

4. **Runtime Code Modification**
   - Enables safe deployment of generated fixes.
   - Tracks state during modifications.
   - Validates applied patches for correctness.

---

## Key Components

### 1. **State Management System**
- Maintains workflow state using Pydantic models.
- Tracks function references, errors, and fixes.
- Ensures type safety and validates execution.

### 2. **LLM Integration**
- Analyzes and generates fixes based on error types, including:
  - Runtime Errors
  - Logic Errors
  - Type Errors
  - Resource Errors

### 3. **Vector-Based Memory System**
- Utilizes ChromaDB for efficient storage and retrieval of bug patterns.
- Enables semantic search and contextual relationships.
- Facilitates pattern-based learning for better error resolution.

### 4. **Graph-Based Workflow**
- Uses LangGraph's StateGraph for orchestration.
- Implements error detection nodes.
- Controls fix generation through directed edges.

---

## Vector Databases and ChromaDB

### What is a Vector Database?
A vector database specializes in handling high-dimensional vectors, capturing semantic meanings for:
- Similarity search operations.
- Pattern recognition.
- Semantic relationships.
- Nearest neighbor queries.

### Why Vector Databases Matter for ML
- Provide semantic search capabilities.
- Support efficient similarity computations.
- Scale with large datasets.
- Maintain context and relationships for advanced pattern recognition.

### ChromaDB Implementation
- **Simple API**:
  ```python
  chroma_client = chromadb.Client()
  collection = chroma_client.create_collection(name='bug-reports')
  ```
- **Easy Data Management**:
  ```python
  # Adding documents
  collection.add(
    ids=[id],
    documents=[document],
  )

  # Querying
  results = collection.query(
    query_texts=[query],
    n_results=10
  )
  ```
- **Capabilities**:
  - Automatic embedding generation.
  - Efficient similarity search.
  - Zero-configuration deployment.

---

## Memory Architecture
### Features:
1. **Vector Storage**
   - Converts bug reports into embeddings.
   - Preserves semantic relationships for efficient similarity searches.

2. **Pattern Recognition**
   - Identifies similar bugs through vector similarity.
   - Leverages historical fixes for new solutions.
   - Tracks pattern evolution over time.

3. **Memory Updates**
   - Integrates new patterns into existing knowledge.
   - Merges and refines related patterns.
   - Prunes obsolete patterns.

---

## Visual Overview
This system uses a graph-based design for orchestrating workflows, from error detection to runtime fixes. (Add flowchart or system diagram here.)

---

## Conclusion
This implementation showcases a practical approach to automated code healing, enriched by vector database technology. It combines graph-based workflow management, LLM capabilities, and vector-based pattern recognition to ensure structured error correction and clear process control.

### Key Advantages:
- Automated error detection and correction.
- Semantic pattern recognition.
- Efficient similarity-based searches.
- Safe runtime code modification.

### Future Improvements:
- Enhanced embedding strategies.
- Multi-modal pattern recognition.
- Distributed vector storage for scalability.
- Advanced tracking of pattern evolution.

This system forms the foundation for building sophisticated self-healing systems for runtime error correction and pattern learning, powered by ChromaDB's efficient vector-based memory management.

---

## How to Get Started
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the workflow:
   ```bash
   python main.py
   ```

4. Explore and query bug patterns using ChromaDB.

---

## Acknowledgments
This project builds upon the original concepts introduced by Nir Diamant and leverages::
- [LangGraph](https://github.com/langgraph)
- [ChromaDB](https://chromadb.com)
- [OpenAI GPT](https://openai.com)

