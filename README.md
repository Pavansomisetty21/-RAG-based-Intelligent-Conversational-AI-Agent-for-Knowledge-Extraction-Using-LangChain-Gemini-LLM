### RAG based Intelligent Conversational AI Agent for Knowledge Extraction using Langchain Gemini LLM


<div align ="center">

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rUJ_wBEYFZsFijDzjOjI8QD9IBeLfB2s?usp=sharing)

</div>
<div align ="center">

### In the above google colab contain detailed code 
</div>


<div align ="center">

   
![image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*SuS0D_-uSf5RnLuUlqgytw.png)

</div>



Retrieval-Augmented Generation (RAG) is a framework that combines information retrieval with generative AI. It allows models to retrieve relevant information from external sources or databases and use that data to generate more accurate and contextually relevant responses. By leveraging both retrieval and generation, RAG improves the accuracy and reliability of AI models, particularly in providing up-to-date information or handling complex questions.

## **Workflow**

This project provides an AI-based conversational assistant that leverages Retrieval-Augmented Generation (RAG) to extract knowledge from PDF documents. The system combines text embeddings, vector search, and an LLM to provide answers to user questions. Below is a detailed step-by-step workflow of how the application operates:

### 1. **Uploading the PDF Document**
   - Users upload a PDF file through the Streamlit interface. The uploaded file is processed to extract the text using `pdfplumber`, a Python library for extracting text from PDFs.
   
### 2. **Text Extraction**
   - The Notebook utilizes the `pdfplumber` library to extract raw text from the uploaded PDF. Each page of the document is parsed, and the resulting text is prepared for further processing.

### 3. **Text Chunking**
   - The extracted text is split into smaller chunks using `RecursiveCharacterTextSplitter`. This ensures the content is manageable for embeddings and retrieval, typically with a chunk size of 500 characters and an overlap of 50 characters.

### 4. **Embeddings Generation**
   - The chunked text is converted into numerical embeddings using `SpacyEmbeddings`. These embeddings represent the semantic meaning of the chunks, enabling efficient search.
     
![Image of embeddings](https://github.com/Pavansomisetty21/RAG-based-Intelligent-Conversational-AI-Agent-for-Knowledge-Extraction-Using-LangChain-Gemini-LLM/blob/main/Images/embedding.jpg)

### 5. **Vector Store with Chroma**
   - A vector database is created using the `Chroma` library, where the embeddings are stored. The vector database allows fast and efficient retrieval of relevant information based on user queries.

### 6. **Conversational Retrieval Chain**
   - The `ConversationalRetrievalChain` is established using `LangChain`, combining the embeddings stored in Chroma with a conversational memory buffer to track chat history and context.

### 7. **LLM Interaction**
   - The Notebook integrates the `ChatGoogleGenerativeAI` (Google's Gemini LLM) to generate relevant and intelligent responses to the user's questions based on the retrieved chunks of text from the vector store.

### 8. **User Query and AI Response**
   - Users can input their questions about the uploaded PDF document, and the system responds by retrieving the most relevant chunks from the vector store and generating an answer using the LLM. The conversation history is preserved for context.

### 9. **Display of Conversation History**
   - The features an expandable section where users can view the conversation history. This transparency allows users to revisit past queries and responses, fostering a better understanding of the context and flow of the interaction.


## RAG Flow in the process 
![rag flow diagram](https://github.com/Pavansomisetty21/RAG-based-Intelligent-Conversational-AI-Agent-for-Knowledge-Extraction-Using-LangChain-Gemini-LLM/blob/main/Images/RAG.jpg)

## **Importance**

1. **Efficient Knowledge Retrieval**: By leveraging the power of RAG, the system combines retrieval and generation to answer specific questions accurately based on the content of uploaded PDF documents.

2. **Scalability and Flexibility**: With text chunking and embeddings, the app can handle large documents while ensuring fast and precise information retrieval.

3. **Conversational AI**: The conversation history memory makes the system more interactive, as it keeps track of previous questions and answers, maintaining context over long conversations.

4. **Integration of Modern AI Tools**: This project demonstrates the use of advanced tools like `Chroma` for vector storage, `LangChain` for conversation management, and Google's `Gemini LLM` for generating human-like answers.

