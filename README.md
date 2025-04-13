# DM Project Suggestions

A Gradio-based web app that recommends machine learning projects for B.Tech CSE students based on their interest bios. Deployed on Hugging Face Spaces for easy access.

[![Hugging Face Space](https://img.shields.io/badge/Hugging%20Face-Space-blue)](https://huggingface.co/spaces/sharan1/DM_Project_Suggestions_V2)

## Overview
This project helps students discover ML projects tailored to their interests (e.g., health, marketing, movies). Built with scikit-learn and Gradio, it’s a teaching tool to introduce 2nd-year B.Tech CSE students to ML and deployment.

- **Live Demo**: [DM Project Suggestions V2](https://huggingface.co/spaces/sharan1/DM_Project_Suggestions_V2)
- **Purpose**: Recommend projects like "Patient disease risk analysis" or "Customer segmentation" based on student bios.
- **Audience**: B.Tech CSE students learning ML basics.

## Features
- **Bio Input**: Enter a short bio (e.g., "I love health data") to get a project suggestion.
- **Suggested Bios**: Try these for quick testing:
  1. I want to predict diabetes with Python
  2. I like analyzing marketing data
  3. I’m curious about movie genres and coding
- **Feedback**: In-app feedback button to share reactions (saved to `feedback.csv`).
- **Accuracy**: Trained model achieves 78.26% accuracy on 230 student bios.

## Technical Details
- **Dataset**: 230 student bios with project labels (e.g., "Patient disease risk analysis").
- **Model**: LogisticRegression with TF-IDF vectorizer (2000 features).
  - Preprocessing: Text to TF-IDF vectors.
  - Training: 230 samples, no train-test split for max data use.
  - Output: Predicts one of ~30 project classes.
- **Files**:
  - `app.py`: Gradio app with bio input, prediction, and feedback.
  - `recommender.pkl`: Single file with vectorizer and model.
  - `requirements.txt`: Lists dependencies (Gradio, scikit-learn, pandas).
- **Deployment**: Hosted on Hugging Face Spaces (free tier, public access).
- **Analytics**: 
  - Feedback saved to `feedback.csv` (bio, suggestion, comment).
  - Google Form for additional student reactions.
  - Planned: Usage counter via `usage_count.json`.
