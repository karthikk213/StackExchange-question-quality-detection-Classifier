# StackExchange-question-quality-detection-Classifier

This project aims to categorize StackOverflow questions into three quality classes: Good, Low, and Very-low quality. The dataset used is from the StackExchange data dump, which contains XML files of posts, users, votes, etc. We only use the Posts.xml file to extract the features and labels for our classifier.

### Dataset
The dataset used in this project can be downloaded from here. The Posts.xml file contains all the questions and answers posted on the StackOverflow website. We use the score, answer_count, body_length, title_length, and comment_count features to classify each question into one of the three quality categories.

### Feature Extraction
We extract the following features from each question:

ID: unique identifier for each question
Score: the number of upvotes minus downvotes
Viewcount: the number of times the question was viewed
Body length: the length of the question body
Title length: the length of the question title
Answer count: the number of answers to the question
Comment count: the number of comments on the question

### Preprocessing
We remove outliers using the IQR method and done undersampling to balance the dataset. We also removed inefficient features that did not contribute significantly to the classification accuracy.

### Models
We trained three models: Logistic Regression, Multinomial Naive Bayes, and Random Forest. All models performed well, but Random Forest achieved the highest accuracy of 99% on the real-time dataset.

### How to run the code
Download the dataset from the above link and extract the Posts.xml file.
Clone this repository.
Open the Jupyter notebook StackOverflow_Question_Quality_Classifier.ipynb.
Run the code cells to preprocess the data, train the models, and evaluate their performance.
Use the trained model to predict the quality of new questions.

### Conclusion
In this project, we have shown how to classify StackOverflow questions into three quality categories using various features and machine learning models. The Random Forest model achieved the highest accuracy of 99% on the real-time dataset. This project can be extended to other StackExchange websites and can be used to automatically flag low-quality questions for moderation.

### Learning Outcomes:
  * Parsing XML files
  * Data Preprocessing techniques
  * Learnt operation of multi class classification models


### Post-analysis Questions:
1. Clearly mention and explain the preprocessing phase. Why did you choose a
particular pre-processing step?

Ans : I done removing outliers and under sampled the dataset to balance the datset. most of the features had non normal distubution , which is right positive skewed.So
I decided to do IQR method to remove outliers. Z-score method will be widely used for normal distribution of datas. good category data is very less compare to other class data, so i decided to undersampe, because it will randomly create a real datas, rather than creating fake datas using upsampling.

2. Explain your choice of model and why do you think it performs well?

Ans : My choice of model is random Forest. it has higher accuracy, best suits for multi class classification.
Reason is Dataset. I done well preprocessed and cleaned dataset, so it trained the model above the expected level. 
