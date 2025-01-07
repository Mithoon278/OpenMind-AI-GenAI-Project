# **OPENMIND_AI-RAG PROJECT**

This project implements a mental support chatbot using a Retrieval-Augmented Generation (RAG) framework. The chatbot is designed to provide compassionate, thoughtful, and context-aware responses by leveraging pre-existing datasets and integrating advanced natural language processing techniques.

---

## **Project Overview**
The chatbot:
- Uses a csv file of psychological contexts and responses to generate insightful answers.
- Embeds data using `SentenceTransformers` and stores it in a Pinecone vector database.
- Retrieves relevant context dynamically during conversation.
- Fine-tunes an LLM model to act as a compassionate, friendly personal assistant.
- Processes queries to provide meaningful, concise, and empathetic responses.

---

## **Workflow**
1. **Data Preprocessing**:
   - The data is taken from [huggingface](https://huggingface.co/datasets/jkhedri/psychology-dataset/viewer/default/train?p=1), removed the third column from it because of irrelevant responses.
   - Converted to csv using pandas.
   - Load the dataset using LangChain's CSVLoader.
   - Format the data into question-answer pairs.
2. **Text Chunking**:
   - Use LangChain's `RecursiveCharacterTextSplitter` for chunking large texts.
3. **Embeddings**:
   - Generate vector embeddings using `SentenceTransformers` (`all-MiniLM-L6-v2`).
4. **Storage**:
   - Store embeddings in Pinecone for fast and scalable retrieval.
5. **Retrieval-Augmented Generation**:
   - Retrieve context based on user queries.
   - Use LLaMA 3.2 for generating responses augmented with retrieved context.

---

## **Technologies Used**
- Language Models: LLaMA 3.3
- Embeddings: SentenceTransformers (all-MiniLM-L6-v2)
- Database: Pinecone
- Frameworks: LangChain, Streamlit
- Programming Language: Python
