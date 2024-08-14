# Q&A Generator 📚❓

This FastAPI project allows users to upload PDF files, generate questions from the content using OpenAI's GPT-3.5-turbo, and then answer those questions using a retrieval-based QA model. The results are saved in a CSV file, which can be downloaded. 📥

## Features ✨

- **PDF Upload**: Upload PDF documents for processing. 📄
- **Question Generation**: Generate exam-oriented questions from the PDF content using OpenAI's language models. 📝
- **Answer Generation**: Answer the generated questions using a retrieval-based model. 💡
- **CSV Output**: Export the questions and answers to a CSV file. 📊

## Installation 🛠️

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/qa-generator.git
   cd qa-generator
   ```

2. **Create and Activate Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables**:
   - Create a `.env` file in the root directory.
   - Add your OpenAI API key:
     ```
     OPENAI_API_KEY=your_openai_api_key
     ```

## Usage 🚀

1. **Start the Server**:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   ```

2. **API Endpoints**:
   - `GET /`: Render the main page for uploading and processing PDFs. 🌐
   - `POST /upload`: Upload a PDF file. 📤
   - `POST /analyze`: Analyze the uploaded PDF and generate the Q&A CSV file. 🧐

## Code Overview 🔍

Here’s a brief overview of the main components of the project:

- **File Processing**: Reads the PDF content and splits it into chunks for question and answer generation. 🔨
- **Question Generation**: Utilizes OpenAI’s GPT-3.5-turbo to generate relevant questions from the PDF content. 🤖
- **Answer Generation**: Implements a retrieval-based QA system using FAISS for embedding and OpenAI’s language model for answering. 💬
- **CSV Export**: Stores the questions and answers in a CSV file located in the `static/output/` directory. 📂

## Dependencies 📦

- `FastAPI`: Web framework for building APIs. 🌐
- `uvicorn`: ASGI server for FastAPI. 🚀
- `aiofiles`: For async file operations. ⚙️
- `PyPDF2`: To read and process PDF files. 📚
- `langchain`: Toolkit for building applications using LLMs. 🛠️
- `faiss`: For efficient similarity search and clustering of dense vectors. 🧠
