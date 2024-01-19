# CS412 (Machine Learning) Term Project

![Student working on ML Homework](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/DALL%C2%B7E%202024-01-17.png?raw=true)
##### <p align="center">Student working on ML Homework with some AI help. Credit: DALL-E</p>


## Overview of the Repository

This repository contains various scripts and code pieces used to analyze and predict grades based on ChatGPT interactions. The primary dataset includes HTML files of ChatGPT prompts/answers and a Jupyter notebook (assignment.ipynb) containing assignment questions. The project's main Jupyter notebook is [here](Project-Notebooks/Main_Project_Notboook.ipynb) and [![Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DLr98rnqzgORzFtDEM4QTKVzRmVhtSPi?usp=sharing)

### Key Components

1. [Data Extraction and Imputation](Project-Notebooks/Sub-Notebooks/Data-Extraction-and-Imputation.ipynb)
: Extracted text from HTML files of ChatGPT prompts to a JSON file. For IDs with missing text, imputed text from files with mode size.
   + Question-Answer Pair Extraction: Analyzed chat texts to extract question-answer pairs from them. Questions start with "Anonymous" and responses with "ChatGPTChatGPT".
   + Reading Assignment Questions: Extracted questions from the assignment.ipynb, specifically from markdown cells in the "source" part.  
2. [Data Visualization](Project-Notebooks/Sub-Notebooks/Data-Visualization.ipynb): Visualized score data to understand the distribution and identify null data.  
3. [Similarity Calculation](Project-Notebooks/Sub-Notebooks/Similarity-Calculation.ipynb): Computed similarities between assignment questions and user prompts, adding this data to the JSON file for each ID and each question.  
4. [Histograms of Similarities](Project-Notebooks/Sub-Notebooks/Histograms-of-Similarities.ipynb): Plotted histograms of similarities for each question and each ID, calculating average similarity as a predictive feature.  
5. [Linear Regression Models](Project-Notebooks/Sub-Notebooks/Linear-Regression-Models.ipynb): Multiple linear regression models were trained to predict grades based on various features like average similarities, prompt length, number of prompts, average sentiment, and response length.


## **Methodology**

This project adopts a comprehensive and multifaceted approach to predict the scores based on ChatGPT interactions. The methodology employed in this project encompasses various stages of data processing, feature extraction, and predictive modeling, each contributing to the overarching goal of understanding and predicting user scores.

### Data Processing and Preparation
- **Data Extraction**: The project begins with the extraction of ChatGPT interactions from HTML files. Special attention is given to handle malformed files, where missing data is imputed using the text from files with the mode file size, ensuring a complete dataset for analysis.
- **Data Visualization**: Initial exploration of the `scores.csv` data involves visualization to assess the distribution of scores and identify any missing data, which is subsequently imputed using the mean of the column.

### Feature Engineering
- **Extraction of Question-Answer Pairs**: The project focuses on extracting question and answer pairs from ChatGPT interactions, identifying questions with "Anonymous" and responses with "ChatGPTChatGPT".
- **Assignment Question Analysis**: Questions from the `assignment.ipynb` are extracted and analyzed, particularly from markdown cells in the "source" part.
- **Similarity Calculation**: A key aspect of the methodology involves calculating the similarities between the text of assignment questions and user prompts, integrating this information into the dataset for each user ID.

### Predictive Modeling
- **Development of Linear Regression Models**: Various features such as average similarities, prompt length, number of prompts, average sentiment, and the length of GPT responses are utilized to train linear regression models.
- **Performance Evaluation**: Each model's effectiveness is assessed using Mean Squared Error (MSE) and R-squared values, allowing for a comparative analysis of different predictive features.

### Insights and Conclusions
- **Comparative Analysis of Features**: The project identifies which features have the most significant impact on predicting scores. It was observed that the number of prompts and the total number of words in prompts show relatively better predictive performance.
- **Iterative Approach**: The project's methodology is iterative, constantly refining the features and models based on the insights gained from data analysis and model evaluations.

Overall, the project methodology is characterized by its data-driven approach, leveraging natural language processing techniques and statistical modeling to derive meaningful insights and predictions from ChatGPT interactions.

## Results

The experimental findings are supported by various figures and the following table summarizes the model performances. 

#### Performance of the Models:


| Feature                            | Mean Squared Error | R-squared Score |
|-----------------------------------------|--------------------|-----------------|
| Average Similarities                    | 41.99              | -0.40           |
| Total Number of words in Prompts        | 56.67              | -0.89           |
| Number of Prompts                       | 55.60              | -0.85           |
| Average Sentiment                       | 40.74              | -0.36           |
| Average Prompt Length                   | 41.57              | -0.39           |
| Average Response Length                 | 38.43              | -0.28           |
| Average Response Length                 | 38.43              | -0.28           |
| Frequency of "error" in Prompts         | 43.16              | -0.44           |
| Back-to-Back "Error" Counts in Prompts  | 45.08              | -0.50           |

<br />
The observed results demonstrate a varied level of accuracy and effectiveness across different features in the prediction of scores. Despite the careful approach taken in the project, the limited size of the dataset and the narrow standard deviation, where 50% of the scores exceed 72, result in the models exhibiting relatively large errors in their predictions.

#### Figures (Features vs Grades):

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avgsim.png?raw=true)
##### <p align="center">Fig 1. Average Similarities of Prompts/Assignment-Questions vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/promptnumofwords.png?raw=true)
##### <p align="center">Fig 2. Number of words in Prompts vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/numofprompts.png?raw=true)
##### <p align="center">Fig 3. Number of prompts vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avgsentiment.png?raw=true)
##### <p align="center">Fig 4. Average Sentiment of Prompts vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avglengthprompts.png?raw=true)
##### <p align="center">Fig 5. Average Prompt Length vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/avglengthresponses.png?raw=true)  
##### <p align="center">Fig 6. Average GPT Response Length vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/errors.png?raw=true)  
##### <p align="center">Fig 7. Frequency of "error" in Prompts vs Grades</p><br />

![avgsim vs grades](https://github.com/Miladbaf/CS412_Term_Project/blob/main/Project-Notebooks/backtoback-errors.png?raw=true)  
##### <p align="center">Fig 8. Back-to-Back "Error" Counts in Prompts vs Grades</p><br />

## Team Contributions

Milad Bafarassat: As the sole contributor to this project, I was responsible for all aspects, including data extraction and preprocessing, feature engineering, model development, analysis, and documentation. My role encompassed the entire pipeline from initial data handling to final model evaluation and reporting of findings.

