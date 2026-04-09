RAG Chatbot for Full Stack Academy (Gradio + OpenRouter + FAISS)
This project implements a simple Retrieval-Augmented Generation (RAG) chatbot designed to answer questions about Full Stack Academy, leveraging both website content and a CSV file as data sources. The chatbot is built using LangChain, utilizes FAISS for vector storage, and is served via a Gradio interface. It integrates with OpenRouter for language model access.

Features
Web Scraping: Automatically extracts information from the Full Stack Academy website (https://fullstackacademy.in/).
CSV Data Ingestion: Incorporates structured data from a course.txt file (simulating course details).
Vector Database: Uses FAISS to create an efficient vector store for document retrieval.
OpenRouter Integration: Connects to language models via the OpenRouter API for generating responses.
Gradio User Interface: Provides an interactive web-based chat interface for easy interaction.
Technologies Used
Python
LangChain
Gradio
Requests & BeautifulSoup4 (for web scraping)
FAISS (for vector similarity search)
OpenAI Embeddings (via OpenRouter)
ChatOpenAI (via OpenRouter for LLM)
Pandas (for data handling)
Setup and Installation
Clone the Repository:

git clone <your-repository-url>
cd <your-repository-name>
Install Dependencies: It's recommended to use a virtual environment.

pip install -r requirements.txt
(Create a requirements.txt from your notebook's !pip install commands) A sample requirements.txt might look like this:

langchain-openai
langchain
faiss-cpu
pandas
requests
beautifulsoup4
openai
gradio
tiktoken
langchain-text-splitters
langchain-google-genai
langchain-community
langchain-huggingface
langchain-classic
Obtain API Keys:

OpenRouter API Key: Sign up at OpenRouter and generate an API key. This key will be used to access various language models.
Configure API Keys: Create a .env file in the project root or set environment variables directly:

OPENROUTER_API_KEY="sk-or-v1-..."
GOOGLE_API_KEY="AIzaSyB..." # If using Gemini, which is optionally included in the notebook
Alternatively, set them in your Python script/notebook as shown in the Colab notebook:

import os
OPENROUTER_API_KEY = "sk-or-v1-YOUR_OPENROUTER_KEY"
os.environ["OPENAI_API_KEY"] = OPENROUTER_API_KEY
os.environ["OPENAI_API_BASE"] = "https://openrouter.ai/api/v1"

# For Google Gemini (if used)
# os.environ["GOOGLE_API_KEY"] = "YOUR_GOOGLE_API_KEY"
Prepare Data: Ensure you have a course.txt file in your project directory (or adjust the path in the notebook) with your course data. For example:

course\tduration\ttiming\ttrainer_name
Data Science\t4 months\t7pm-9pm\tVarun Maya
AI Specialist\t3 months\t8pm-10pm\tRahul Verma
...
How to Run
Execute the Colab Notebook: Open the .ipynb file in Google Colab and run all cells sequentially. The notebook performs the following steps:

Installs necessary libraries.
Sets up API keys.
Scrapes data from the Full Stack Academy website.
Loads data from course.txt.
Combines and chunks the text data.
Creates a FAISS vector store with embeddings.
Initializes the RAG qa_chain.
Launches the Gradio interface.
Access the Chatbot: Once the Gradio interface launches (after running the last cell), it will provide a local URL and potentially a public share link. Open this URL in your web browser to interact with the chatbot.

Usage
Type your questions related to Full Stack Academy's courses, trainers, placements, or general information into the chat interface and press Enter. The chatbot will retrieve relevant information from its knowledge base and generate a response.

Example Questions:

"What courses does Full Stack Academy offer?"
"Who is the trainer for Data Science?"
"What is the duration of the AI Specialist course?"
"How many students have been placed?"
Project Structure
your_notebook_name.ipynb: The main Colab notebook containing all the code.
course.txt: The CSV file containing structured course data.
README.md: This file.
Future Enhancements
Implement chat history persistence.
Add support for more diverse data sources (e.g., PDFs, databases).
Improve response generation with more advanced LLM techniques.
Enhance error handling and user feedback.
