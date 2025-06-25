# Corrective RAG (Agentic RAG)

This project demonstrates a Corrective Retrieval-Augmented Generation (RAG) architecture using LangChain, Google Generative AI, and web search. The notebook implements an agentic workflow that corrects or supplements answers using external data sources (web search) when the retriever cannot provide a relevant response.

## Features

- **Retriever-Augmented Generation**: Combines vector search with LLMs for context-aware answers.
- **Corrective Workflow**: If retrieved documents are not relevant, the system rewrites the query and performs a web search to improve the answer.
- **Web Search Integration**: Uses TavilySearchResults to fetch up-to-date information from the web.
- **Document Grading**: Automatically grades the relevance of retrieved documents using an LLM-based grader.
- **Agentic State Graph**: Orchestrates the workflow using LangGraph's stateful graph execution.

## How It Works

1. **Retrieve**: Fetch documents relevant to the user's question from a local vector database.
2. **Grade**: Use an LLM to check if the retrieved documents are relevant.
3. **Transform Query**: If not relevant, rewrite the question for better web search results.
4. **Web Search**: Search the web for additional information and append results.
5. **Generate**: Use the LLM to generate a final answer based on all available documents.

## Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone <your-repo-url>
   cd Corrective-RAG
   ```

2. **Install Dependencies**

   Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up API Keys**

   Create a `.env` file in the project directory with the following keys (see sample below):

   ```env
   GROQ_API_KEY="<your-groq-key>"
   LANGCHAIN_API_KEY="<your-langchain-key>"
   LANGCHAIN_PROJECT="Agentic-Corrective-RAG"
   LANGCHAIN_TRACING_V2="true"
   GOOGLE_API_KEY="<your-google-key>"
   TAVILY_API_KEY="<your-tavily-key>"
   ```

4. **Run the Notebook**

   Open `corrective_rag.ipynb` in VS Code or Jupyter and run all cells.

## Usage

- Enter a question in the workflow (e.g., "Tell me about Corrective RAG").
- The system will retrieve documents, grade their relevance, and if needed, rewrite the query and perform a web search.
- The final answer is generated using all relevant information.

## Requirements

- Python 3.8+
- See `requirements.txt` for all dependencies.

## Main Components

- `corrective_rag.ipynb`: Main notebook implementing the workflow.
- `.env`: Stores API keys for LLMs and web search.
- `requirements.txt`: List of required Python packages.

## License

This project is licensed under the MIT License.
