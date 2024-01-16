# CS412_Term_Project

Overview of the Repository
This repository contains various scripts and code pieces used to analyze and predict grades based on ChatGPT interactions. The primary dataset includes JSON files of ChatGPT prompts and a Jupyter notebook (assignment.ipynb) containing assignment questions.

Key Components:

Data Extraction and Imputation: Extracted text from JSON files of ChatGPT prompts. For IDs with missing text, imputed text from files with mode size.
Data Visualization: Visualized score data to understand the distribution and identify null data.
Question-Answer Pair Extraction: Analyzed chat texts to extract question-answer pairs. Questions started with "Anonymous" and responses with "ChatGPTChatGPT".
Reading Assignment Questions: Extracted questions from the assignment.ipynb, specifically from markdown cells in the "source" part.
Similarity Calculation: Computed similarities between assignment questions and user prompts, adding this data to the JSON file for each ID.
Histograms of Similarities: Plotted histograms of similarities for each question and each ID, calculating average similarity as a predictive feature.
Linear Regression Models: Multiple linear regression models were trained to predict grades based on various features like average similarities, prompt length, number of prompts, average sentiment, and response length.


Methodology
The project employed a data-driven approach, focusing on feature extraction from text data, sentiment analysis, and statistical modeling. The methodology involved cleaning and preprocessing text data, utilizing natural language processing techniques for sentiment analysis, and applying linear regression models for predictive analysis.

Results
The experimental findings are supported by various figures (to be added) and the following table summarizing the model performances:

Performance of the Models:

Average Similarities: MSE = 41.99, R² = -0.40
Prompt Length: MSE = 56.67, R² = -0.89
Number of Prompts: MSE = 55.60, R² = -0.85
Average Sentiment: MSE = 40.74, R² = -0.36
Total Prompt Length: MSE = 41.57, R² = -0.39
Average Response Length: MSE = 38.43, R² = -0.28
The results suggest that the average length of GPT responses and sentiment of prompts have better performance in predicting grades.

The results indicate varying degrees of correlation between different features and grades, with the average length of GPT responses and sentiment analysis of prompts showing relatively better predictive performance.

Team Contributions
Milad Bafarassat: As the sole contributor to this project, I was responsible for all aspects, including data extraction and preprocessing, feature engineering, model development, analysis, and documentation. My role encompassed the entire pipeline from initial data handling to final model evaluation and reporting of findings.

