Log Classification – Hybrid Classification Framework

This project implements a hybrid log classification system that combines multiple approaches to handle different levels of complexity in log patterns. It is designed to classify both simple and complex log data efficiently.

Key Idea

Different types of logs require different classification methods. This framework combines rule-based, machine learning, and language model approaches to improve flexibility and accuracy.

Classification Approaches
1. Regular Expression (Regex)

Handles simple and predictable log patterns using predefined rules. This method is fast and works well for structured logs.

2. Sentence Transformer + Logistic Regression

Handles more complex patterns when training data is available. Log messages are converted into embeddings using Sentence Transformers, and Logistic Regression is used for classification.

3. Large Language Models (LLMs)

Used for complex cases where labeled training data is limited. Acts as a fallback method and provides context-aware classification.

Project Structure

training folder contains the code for training models, including Sentence Transformer and Logistic Regression training, as well as regex-based classification logic.

models folder stores trained models, including embeddings and the Logistic Regression model.

resources folder contains datasets, output files, and supporting images or files.

The root directory contains the FastAPI server file (server.py).

Setup Instructions
Install Dependencies
Install all required Python packages using requirements.txt.
Run FastAPI Server
Start the server using uvicorn server:app --reload.
Access API
Once the server is running, you can use:
http://127.0.0.1:8000/ for the main API
http://127.0.0.1:8000/docs for Swagger documentation
http://127.0.0.1:8000/redoc for alternative documentation
Usage

Upload a CSV file containing logs to the API for classification.

Required columns in the CSV:

source
log_message
Output

The system returns a CSV file with an additional column called target_label, which contains the predicted classification result for each log entry.

Highlights
Hybrid approach combining rule-based, machine learning, and LLM methods
Designed for both structured and unstructured logs
Scalable FastAPI backend
Flexible for real-world log classification use cases
