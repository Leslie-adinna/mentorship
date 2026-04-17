PROJECT REPORT
Auto-Complete System for Nigerian Pidgin Using tiny llama
Introduction
Nigerian Pidgin is a widely spoken informal language across Nigeria, used in everyday communication, social media, and entertainment. Despite its popularity, there are limited Natural Language Processing (NLP) tools tailored for Pidgin.
This project focuses on developing an auto-complete system for Nigerian Pidgin using a fine-tuned GPT-2 model, combined with a backend API and a simple user interface for real-time interaction.
Objectives
Collect and preprocess a Nigerian Pidgin dataset
Fine-tune a model
Build an API for inference
Develop a simple front-end interface
Evaluate performance and usability
Problem Statement
Most existing auto-complete systems are optimized for standard English and do not effectively support Nigerian Pidgin due to:
Lack of structured datasets
Informal and inconsistent spelling
Limited NLP tools for low-resource languages
This creates a gap in digital communication tools for millions of Pidgin speakers.
Proposed Solution
This project proposes:
Fine-tuning a model on Nigerian Pidgin text
Building an API to serve the model
Creating a simple UI that interacts with the model
The goal is to enable real-time Pidgin text auto-completion.
Background
Auto-Complete Systems
Auto-complete systems predict the next word or phrase based on previously typed text. These systems are widely used in search engines, messaging apps, and code editors.

Methodology
Data Collection
The dataset used in this project consists of over 12,000+ Pidgin text samples collected from:
BBC Pidgin
Online forums
Conversational datasets
Data Preprocessing
Data preprocessing was performed before training to reduce computational load. The dataset used during training was already cleaned, which helped prevent GPU memory issues.
Steps included:
Removing noise and duplicates
Normalizing text
Formatting into a single column dataset
Model Selection
tiny llama was selected due to:
Its strong text generation capabilities
Availability of pre-trained weights
Compatibility with limited computational resources
Model Training (Python Notebook)
The model training process was implemented in a Python notebook and includes:
Loading model and tokenizer
Encoding dataset
Training using causal language modeling
Saving trained model locally
Key Training Details
Model: tiny llama
Framework: Hugging Face Transformers
Environment: Google Colab + External compute system
GPU: Tesla T4
Compute Challenges
GPU memory limitations on Colab
Runtime disconnections
GPU allocation time limits
Fine-Tuning Process
The model was fine-tuned using the following steps:
Load pre-trained tiny llama tokenizer and model
Encode the dataset into token sequences
Train using causal language modeling objective
Optimize using AdamW optimizer
Train for multiple epochs with checkpoint saving
Training environment:
Platform: Google Colab
GPU: Tesla T4
Framework: Hugging Face Transformers 
Optimization Applied
Reduced epochs from 5 to 3 to avoid memory crashes
Used already-cleaned dataset to reduce preprocessing load
System Architecture
The system is divided into three main components:
Model Layer
Fine-tuned tiny llama model
Stored separately (not included in repo due to size)
Backend (API Layer)
Built using FastAPI
Handles requests from UI
Sends input text to model
Returns generated predictions
Flow: User Input → API Request → Model Inference → Response
Frontend (UI Layer)
Simple interface (HTML-based)
Sends user input to API
Displays auto-complete suggestions
Implementation
Libraries Used
Python
Hugging Face Transformers
PyTorch
Datasets
Backend - Fast API
Frontend - Gradio
Observations
API Integration
FastAPI endpoint receives input text
Calls model.generate()
Returns predictions as JSON
Deployment
Application hosted online
Accessible via shared link
Model hosted separately (e.g., Google Drive due to size)
The model generates coherent Pidgin text
Predictions improve with more training data
Some inconsistencies due to informal spelling variations
The model used 4 hrs 20 mins for training.

Challenges
GPU memory limitations (T4 constraints)
Runtime timeouts in Colab
Large model size (cannot upload directly to GitHub)
Informal nature of Pidgin language
Results
The fine-tuned tiny llama model successfully:
Learned Pidgin sentence structures
Generated relevant next-word predictions
Improved typing efficiency in test scenarios
Example:
Input: "I dey go" Output: "I dey go market later today"
Conclusion
This project demonstrates a complete pipeline for building a Pidgin auto-complete system—from data preparation and model training to deployment and user interaction. Despite computational challenges, the system provides meaningful results and shows strong potential for real-world applications.
