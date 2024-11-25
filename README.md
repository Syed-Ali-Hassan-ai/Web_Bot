
# Chat with Website 🦜🔗

This Streamlit application allows users to interact with the content of a website by asking questions. The application retrieves answers directly from the website content using an AI-powered retrieval system.

---

## Features

- **Website Data Loading:** Extracts content directly from a specified website URL.
- **Text Splitting:** Splits the extracted text into chunks for efficient processing.
- **Embeddings with Ollama:** Utilizes the Mistral model for embedding text chunks.
- **Chroma Vector Store:** Stores document embeddings for semantic search.
- **Retrieval QA System:** Allows users to ask questions and receive AI-generated answers based on the website content.

---

## Requirements

### Dependencies

The following Python packages are required:
- `streamlit`
- `langchain`
- `langchain-community`
- `chromadb`

Install them using pip:

```bash
pip install streamlit langchain langchain-community chromadb
```

---

## Setup and Usage

1. Clone this repository or copy the code into a Python script.
2. Install the required dependencies using the above command.
3. Run the Streamlit app:

   ```bash
   streamlit run your_script_name.py
   ```

4. Enter the website URL in the script (replace `Your Website Name`).
5. Type your question or query in the input field and click "Submit Query."

---

## Code Breakdown

### `main()`
The primary function to manage the app workflow, including:
- Setting up the app UI with Streamlit.
- Accepting user input for a website URL and query.
- Loading website content using `WebBaseLoader`.
- Splitting website data into manageable chunks using `CharacterTextSplitter`.
- Creating document embeddings with the Mistral model via `OllamaEmbeddings`.
- Storing embeddings in a persistent Chroma vector database.
- Setting up a retriever for semantic search.
- Answering user queries with a RetrievalQA system using the Mistral LLM.

---

## Environment Variables (Optional)

To use LangChain tracing or connect to specific APIs, the following environment variables can be set in a `.env` file:
- `LANGCHAIN_TRACING_V2`
- `LANGCHAIN_ENDPOINT`
- `LANGCHAIN_API_KEY`
- `LANGCHAIN_PROJECT`

Use `python-dotenv` to load these variables automatically:
```bash
pip install python-dotenv
```

---

## How It Works

1. **Load Website Content:** The `WebBaseLoader` fetches text data from the specified URL.
2. **Text Splitting:** Breaks down large text data into smaller, overlapping chunks for better processing.
3. **Embeddings Creation:** Embeds text chunks using Ollama’s Mistral model for semantic representation.
4. **Vector Store:** Stores embeddings in a Chroma database, which supports semantic search.
5. **QA System:** The `RetrievalQA` chain retrieves relevant content and generates AI-powered responses to user queries.

---

## Customization

### Model and Embeddings
- Replace the Mistral model with a different Ollama or OpenAI model by modifying the `OllamaEmbeddings` and `Ollama` calls.

### Database Persistence
- Change the database directory by updating the `DB_DIR` variable.

---

## Future Improvements
- Add support for multiple website URLs.
- Improve error handling for website loading issues.
- Introduce multi-user session support for querying multiple websites.

---

## License

This project is released under the MIT License. Feel free to use, modify, and distribute the code.

--- 

## Credits

Developed using:
- [Streamlit](https://streamlit.io/)
- [LangChain](https://www.langchain.com/)
- [Chromadb](https://www.trychroma.com/)
