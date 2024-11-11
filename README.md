# Chat-PDF-using-Google-Gemini-LangChain
This application allows users to interact with PDF documents by asking questions, which the app answers based on the content of the uploaded PDFs. Built with Streamlit, this app uses Google’s Gemini AI, FAISS, and LangChain to extract, embed, and query PDF content efficiently.

# Features
-PDF Upload & Parsing: Users can upload one or more PDFs. The app extracts the text from each file for processing.
-Text Chunking: Extracted text is split into manageable chunks for embedding.
-Vector Storage: FAISS (Facebook AI Similarity Search) is used to create and store vector embeddings for efficient similarity search.
-Conversational AI: Utilizes Google Gemini (via LangChain) to answer questions based on the PDF content.
-Contextual Question Answering: Responses are generated from the most relevant document segments, with the option to indicate when an answer is unavailable.


# Prerequisites
-Python 3.10 or above
-A Google API key with access to the Gemini model and Google Generative AI
-Streamlit, PyPDF2, dotenv, and LangChain installed (see instructions below)

# Installation
-Clone the Repository:
git clone https://github.com/username/repo-name.git
cd repo-name

-Create a Virtual Environment:
python -m venv env
source env/bin/activate   # On Windows, use `env\Scripts\activate`

-Install Dependencies:
pip install -r requirements.txt

Set Up Environment Variables:
-Create a .env file in the root directory.
-Add your Google API key:
GOOGLE_API_KEY=your_google_api_key_here

# How to Run
Start the Streamlit app by running:

streamlit run app.py
This will open the app in your default web browser.

# Usage
-Upload PDFs:
Use the sidebar to upload PDF files.
Click "Submit & Process" to extract and store the content for querying.

# Ask Questions:
Enter a question related to the PDF content in the main input field.
If the content is available, the app will display a detailed answer. If not, it will inform you that the answer is unavailable.


# Code Overview
-PDF Text Extraction: get_pdf_text(pdf_docs) extracts text from each page of uploaded PDFs.
-Text Chunking: get_text_chunks(text) splits the text into chunks for easier processing.
-Vector Store Creation: get_vector_store(text_chunks) creates and saves FAISS embeddings for the text chunks.
-Conversational Chain: get_conversational_chain() sets up a question-answering chain using Google Gemini’s generative capabilities.
-User Interaction: user_input(user_question) retrieves relevant documents based on the user's question and displays the generated answer.
-Streamlit App Layout: main() defines the user interface and handles user inputs.


# Additional Notes
Embeddings: The app uses Google’s embedding model (models/embedding-001) for vector storage with FAISS.
API Keys: Be sure to keep your API keys secure and do not share them publicly.

# Dependencies
Streamlit: For web-based UI
PyPDF2: For PDF text extraction
dotenv: For environment variable management
LangChain & FAISS: For question answering with vector storage and retrieval

Screenshot:
![gemini](https://github.com/user-attachments/assets/4d4be5e3-a326-4408-bce4-9eb08c8f9227)
