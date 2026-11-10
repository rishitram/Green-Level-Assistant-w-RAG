# Green Level High School RAG Chatbot

A Retrieval-Augmented Generation (RAG) chatbot that answers questions about Green Level High School using information retrieved from the school's website. Built with Python, LangChain, Ollama, and Nomic Embeddings, the chatbot uses a locally hosted Llama 3.2 model to generate answers based on relevant school announcements.

## Features

- **Web Scraping:** Extracts school announcements and information using LangChain's WebBaseLoader.
- **Document Processing:** Splits website content into smaller chunks for efficient retrieval.
- **Semantic Search:** Uses Nomic Embeddings and a scikit-learn vector store to find relevant information.
- **Local LLM:** Runs Llama 3.2 (1B) through Ollama to generate responses.
- **Context-Based Answers:** Uses retrieved documents to provide concise answers grounded in school information.

## Tech Stack

- **Language:** Python
- **LLM:** Llama 3.2 (1B) via Ollama
- **Framework:** LangChain
- **Embeddings:** Nomic Embed Text v1.5
- **Vector Store:** scikit-learn (SKLearnVectorStore)
- **Web Scraping:** WebBaseLoader
- **Text Processing:** RecursiveCharacterTextSplitter

## How It Works

1. **Load Documents:** Retrieve school announcements from the Green Level High School website.
2. **Split Text:** Divide documents into chunks of 1,000 tokens with 200-token overlap.
3. **Generate Embeddings:** Convert text chunks into vector embeddings using Nomic.
4. **Store and Retrieve:** Store embeddings in a scikit-learn vector store and retrieve relevant documents based on the user's question.
5. **Generate Answers:** Pass the retrieved context and question to Llama 3.2 to generate a concise response.

## Installation

### Prerequisites

- Python 3.10+
- Jupyter Notebook
- Ollama

Install and start Ollama, then download the language model:

```bash
ollama pull llama3.2:1b
```

Install the required Python packages:

```bash
pip install langchain langchain-community langchain-ollama langchain-nomic "nomic[local]" tiktoken scikit-learn langgraph tavily-python beautifulsoup4
```

## Usage

1. Clone the repository and open the Jupyter notebook.
2. Make sure Ollama is running locally.
3. Run the notebook cells to load the school announcements, generate embeddings, and initialize the retriever.
4. Modify the `question` variable to ask a question about Green Level High School.

Example:

```python
question = "When does the book club meet?"
```

The chatbot retrieves relevant information from the school website and generates an answer.

### Example Output

**Question:**

When does the book club meet?

**Response:**

The Green Level Book Club meets during Connectivity (register with Ms. Beach) on February 11 at 6:00–7:00 pm.

## Future Improvements

- Expand the document collection to cover more school announcements and events.
- Add a simple web interface for students to ask questions.
- Automatically refresh school information as new announcements are published.
- Include source links in generated responses for easier verification.

## Project Overview

This project explores how Retrieval-Augmented Generation can make school information easier to access. Instead of manually searching through announcements, students can ask questions in natural language and receive answers based on retrieved school content.
