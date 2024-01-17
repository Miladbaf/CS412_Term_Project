# CS412 Term Project

![Student working on ML Homework](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/DALL%C2%B7E%202024-01-17.png?raw=true)
<p align="center">Student working on ML Homework with some AI help. Credit: DALL-E</p>


## **Overview of the Repository**

This repository contains various scripts and code pieces used to analyze and predict grades based on ChatGPT interactions. The primary dataset includes HTML files of ChatGPT prompts/answers and a Jupyter notebook (assignment.ipynb) containing assignment questions. Project's main Jupyter Notebook is [here.](Project-Notebooks/Main_Project_Notebook.ipynb)

## **Key Components**

1. [Data Extraction and Imputation](Project-Notebooks/Sub-Notebooks/Data-Extraction-and-Imputation.ipynb)
: Extracted text from HTML files of ChatGPT prompts to a JSON file. For IDs with missing text, imputed text from files with mode size.
   + Question-Answer Pair Extraction: Analyzed chat texts to extract question-answer pairs. Questions started with "Anonymous" and responses with "ChatGPTChatGPT".
   + Reading Assignment Questions: Extracted questions from the assignment.ipynb, specifically from markdown cells in the "source" part.  
2. [Data Visualization](Project-Notebooks/Sub-Notebooks/Data-Visualization.ipynb): Visualized score data to understand the distribution and identify null data.  
3. [Similarity Calculation](Project-Notebooks/Sub-Notebooks/Similarity-Calculation.ipynb): Computed similarities between assignment questions and user prompts, adding this data to the JSON file for each ID.  
4. [Histograms of Similarities](Project-Notebooks/Sub-Notebooks/Histograms-of-Similarities.ipynb): Plotted histograms of similarities for each question and each ID, calculating average similarity as a predictive feature.  
5. [Linear Regression Models](Project-Notebooks/Sub-Notebooks/Linear-Regression-Models.ipynb): Multiple linear regression models were trained to predict grades based on various features like average similarities, prompt length, number of prompts, average sentiment, and response length.


## **Methodology**

The project employed a data-driven approach, focusing on feature extraction from text data, sentiment analysis, and statistical modeling. The methodology involved cleaning and preprocessing text data, utilizing natural language processing techniques for sentiment analysis, and applying linear regression models for predictive analysis.

## **Results**

The experimental findings are supported by various figures and the following table summarizing the model performances:

### **Performance of the Models:**


| Feature                   | Mean Squared Error | R-squared Score |
|---------------------------|--------------------|-----------------|
| Average Similarities      | 41.99              | -0.40           |
| Number of words in Prompts | 56.67              | -0.89           |
| Number of Prompts         | 55.60              | -0.85           |
| Average Sentiment         | 40.74              | -0.36           |
| Average Prompt Length       | 41.57              | -0.39           |
| Average Response Length   | 38.43              | -0.28           |



The results indicate varying degrees of correlation between different features and grades, with the average length of GPT responses and sentiment analysis of prompts showing relatively better predictive performance.

### **Figures:**

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avgsim.png?raw=true)
<p align="center">Fig 1. Average Similarities of Prompts/Assignment-Questions vs Grades</p>  

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/promptnumofwords.png?raw=true)
<p align="center">Fig 2. Number of words in Prompts vs Grades</p>  

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/numofprompts.png?raw=true)
<p align="center">Fig 3. Number of prompts vs Grades</p>  

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avgsentiment.png?raw=true)
<p align="center">Fig 4. Average Sentiment of Prompts vs Grades</p>  

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avglengthprompts.png?raw=true)
<p align="center">Fig 5. Average Prompt Length vs Grades</p>

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avglengthresponses.png?raw=true)
<p align="center">Fig 6. Average GPT Response Length vs Grades</p>

## **Team Contributions**

Milad Bafarassat: As the sole contributor to this project, I was responsible for all aspects, including data extraction and preprocessing, feature engineering, model development, analysis, and documentation. My role encompassed the entire pipeline from initial data handling to final model evaluation and reporting of findings.

