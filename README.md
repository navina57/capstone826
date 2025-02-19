# **Capstone Project: Sentiment Analysis of ChatGPT iOS Store Reviews**

## **Overview**

This project analyzes user reviews of **ChatGPT** on the **iOS App Store** to classify sentiment, extract key product feedback, and identify trends in user satisfaction. Using **Natural Language Processing (NLP)** techniques, the goal is to uncover actionable insights that can inform improvements in **product usability**, **functionality**, and **overall satisfaction**.

## **Problem Statement**

Understanding customer sentiment is crucial for enhancing the user experience of products. This project leverages **sentiment analysis** to automate the extraction of insights from large sets of reviews. The findings can help:

- **Pinpoint areas** for product improvements or innovations
- Identify features with **positive feedback** and those requiring **enhancement**
- **Optimize product features** based on user feedback, particularly for startups with limited resources

### **Objective**:
By automating sentiment analysis, I aim to allow companies to move quickly, prioritize user-driven changes, and increase **customer satisfaction**.

## **Approach**

### **Dataset & Preprocessing**

- **Data Source**: iOS App Store reviews for **ChatGPT**
- **Preprocessing**: Tokenization, stopword removal, lemmatization using **spaCy** to standardize the text data and improve model accuracy.
- **Data Cleaning**: Removing duplicate reviews, handling missing values, and dealing with inconsistencies such as varying date formats.

### **Feature Engineering**:
- **TextBlob** for initial sentiment analysis: Used to calculate sentiment polarity and identify if reviews lean positive, neutral, or negative.
- **VADER** for refined sentiment analysis: A tool specifically tuned for social media and customer reviews that takes into account the usage of emojis, punctuation, and common slang.

### **Exploratory Data Analysis (EDA)**:
- **Sentiment Distribution**: Visualized the overall sentiment of the dataset using **TextBlob** and **VADER**. This provided an understanding of the overall customer satisfaction with the app.
- **Feature Analysis**: Identified the most frequently discussed product features by parsing the reviews using **spaCy**. This allowed me to focus on key areas for product improvement.

### **Key Questions Explored in EDA**:
- What is the overall sentiment towards the product?
- Which features of the product are most frequently mentioned in user reviews?
- Are users generally satisfied or dissatisfied with ChatGPT’s performance on iOS?

## **Modeling**

### **Clustering with K-Means**:
- **Objective**: Group similar reviews to identify distinct customer sentiments regarding the product features.
- **Model Selection**: K-Means was selected due to its ability to uncover patterns and themes within a large dataset of unstructured text.
- **Evaluation Metrics**: 
  - **Elbow Method**: Used to determine the optimal number of clusters by examining the total within-cluster sum of squares.
  - **Silhouette Score**: Used to assess the quality of the clusters formed by K-Means. A silhouette score closer to +1 indicates well-formed clusters.

### **Key Insights from Clustering**:
- **Silhouette Score**: An optimal K-value of 4 was identified based on the silhouette score and elbow curve analysis, suggesting that 4 clusters provide the most accurate groupings.
- **Cluster Composition**: The clusters revealed distinct patterns in sentiment, with some clusters showcasing positive sentiment around certain features, while others identified dissatisfaction with specific aspects of the app.

### **Transition to Supervised Learning (SVM)**:
- **Limitations of K-Means**: While K-Means provided useful clustering, the model’s performance could be improved with a **supervised learning approach**.
- **Support Vector Machines (SVM)**: Transitioning to **SVM** for classification is a natural next step since it is well-suited for labeled data and can provide more accurate results for predicting user sentiment.
- **Dimensionality Reduction**: **Principal Component Analysis (PCA)** will be applied to reduce the feature space and capture the most relevant variance for classification tasks.
  
### **Model Evaluation**:
- **Performance Metrics**: The SVM model will be evaluated using **accuracy**, **precision**, **recall**, and **F1 score**. These metrics will help assess how well the model performs in classifying user reviews into sentiment categories.
  
### **Key Benefits of Using SVM**:
- **Class Imbalance Handling**: SVM is particularly effective at handling class imbalances, which is common in sentiment analysis, where negative reviews may vastly outnumber positive ones.
- **High-dimensional Data**: SVM is ideal for high-dimensional data, especially when dealing with large-scale text data that has been vectorized.

## **Challenges & Insights**

- **Data Quality**: While K-Means produced useful clustering, the lack of labeled data led to less accurate groupings. Transitioning to a supervised model like SVM will provide clearer classifications.
- **Clustering vs. Classification**: K-Means clustering is useful for exploratory analysis, but a supervised approach using **SVM** will provide higher accuracy for sentiment classification.

## **Business Impact**

- **Customer-Centric Insights**: The project allows businesses to quickly analyze large volumes of user feedback and gain insights into areas that need improvement or innovation.
- **Product Roadmap**: By identifying the most discussed features, the model can help inform future product roadmaps and prioritize features based on user feedback.
- **Personalized Marketing**: Understanding specific customer sentiments and preferences can lead to personalized marketing campaigns, improving user retention and engagement.

## **Future Work & Improvements**

- **Feature Expansion**: Incorporate additional features such as **review length**, **emojis**, or **text sentiment intensity** to improve model accuracy.
- **Interactive Dashboard**: Build a **Tableau dashboard** to allow stakeholders to visualize sentiment trends, clusters, and feature relationships dynamically.
- **Data Augmentation**: Gather more reviews from **different platforms** and **product versions** to further refine the model and gain deeper insights into user satisfaction across different user demographics.

## **Conclusion**

This project showcases the potential of **sentiment analysis** and **NLP techniques** in understanding customer feedback at scale. By automating the process of sentiment extraction from reviews, businesses can unlock valuable insights into user satisfaction and product performance. Transitioning from clustering to a supervised classification model using **SVM** will provide a more robust solution to accurately identify sentiment in user reviews, ultimately helping product teams make data-driven decisions that enhance customer experience and satisfaction.

---
