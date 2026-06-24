Log Classification – Hybrid Classification Framework

This project implements a hybrid log classification system that combines multiple approaches to handle varying levels of complexity in log patterns. The system is designed to efficiently classify logs ranging from simple rule-based patterns to complex, ambiguous cases.

Key Idea

Different log patterns require different strategies. This framework integrates multiple classification techniques to ensure flexibility, scalability, and accuracy.

Classification Approaches
1. Regular Expression (Regex)
Handles simple and highly predictable log patterns
Uses predefined rules for fast and efficient classification
Best suited for structured and repetitive logs
2. Sentence Transformer + Logistic Regression
Handles complex patterns with sufficient labeled data
Converts log messages into embeddings using Sentence Transformers
Applies Logistic Regression for final classification
3. Large Language Models (LLMs)
Used for complex or unseen patterns
Acts as a fallback when labeled training data is limited
Provides flexible, context-aware classification
Project Structure
training/
├── Contains model training scripts
├── Includes Sentence Transformer + Logistic Regression training
├── Regex-based classification logic

models/
├── Saved trained models
├── Sentence Transformer embeddings
├── Logistic Regression model files

resources/
├── Sample datasets (CSV files)
├── Output files
├── Images and supporting assets

server.py
├── FastAPI backend for serving the model
Setup Instructions
1. Install Dependencies

Make sure Python is installed, then run:

pip install -r requirements.txt
2. Run FastAPI Server
uvicorn server:app --reload
3. Access the API

Once the server is running, open:

Main API → http://127.0.0.1:8000/
Swagger Docs → http://127.0.0.1:8000/docs
ReDoc → http://127.0.0.1:8000/redoc
Usage

Upload a CSV file containing logs to the API endpoint for classification.

Required Columns:
source
log_message
Output

The system returns a CSV file with an additional column:

target_label → predicted classification label for each log entry
