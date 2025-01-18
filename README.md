# Phishing Detection System

## Overview
This repository contains a web application built with Django that uses a pre-trained machine learning model from Hugging Face to analyze email content and detect phishing attempts. The app stores phishing sender names in a database and allows users to search for them through a simple interface.

## Features
1. **Model Comparison**: We evaluated the performance of three different machine learning models on the dataset `Phishing_Email.csv` from [Kaggle](https://www.kaggle.com/datasets/subhajournal/phishingemails/data). The evaluated models were:
   - `ealvaradob/bert-finetuned-phishing`
   - `cybersectony/phishing-email-detection-distilbert_v2.4.1`
   - `imanoop7/bert-phishing-detector`

   The evaluation metrics included:
   - Recall
   - Accuracy
   - F1-score

   Based on these results, the most effective model was `cybersectony/phishing-email-detection-distilbert_v2.4.1`, which was selected for deployment.

2. **Django Web Application**:
   - Users can input an email's content and sender information through a web-based form.
   - The application scans the email for phishing indicators using the selected AI model.
   - If the email is identified as phishing, the sender is added to a database of potentially dangerous entities.

## Dataset
The dataset used for training and evaluation, `Phishing_Email.csv`, is publicly available on Kaggle. It includes various features extracted from phishing and legitimate emails to train the models effectively.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/WojtekBoboryk/phishing-detection.git
   cd phishing-detection
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # For Linux/Mac
   venv\Scripts\activate   # For Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Migrate the Django database:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Run the development server:
   ```bash
   python manage.py runserver
   ```

## Usage
1. Open the Django application in your browser at `http://127.0.0.1:8000`.
2. Paste the email content and sender's information into the provided form.
3. Click the **Analyze** button to analyze the email.
4. If the email is flagged as phishing, the sender will be added to the database of potentially dangerous entities.

## Model Evaluation
During the initial phase of the project, we tested three machine learning models on the `Phishing_Email.csv` dataset. The evaluated models were:
- `ealvaradob/bert-finetuned-phishing`
- `cybersectony/phishing-email-detection-distilbert_v2.4.1`
- `imanoop7/bert-phishing-detector`

The evaluation process focused on key metrics:
- **Recall**: To measure the ability of the model to detect phishing emails correctly.
- **Accuracy**: To determine the overall correctness of predictions.
- **F1-score**: To balance precision and recall for better decision-making.

The best-performing model was `cybersectony/phishing-email-detection-distilbert_v2.4.1`, which demonstrated the highest effectiveness and was integrated into the Django application.

## Acknowledgments
- The dataset used in this project is provided by [Kaggle](https://www.kaggle.com/datasets/subhajournal/phishingemails/data)).
- The models used in this project are pre-trained and provided by their respective authors: `ealvaradob`, `cybersectony`, and `imanoop7`.


---
Feel free to reach out if you have questions or suggestions for improving the system!

