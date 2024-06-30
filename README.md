# Analysis-of-Abstract-using-Text-Mining

## Overview

This case study analyzes a dataset of 4385 research papers published between 2000 and 2022 across three major journals: the Journal of the Operational Research Society, Health Systems, and the Journal of Simulation. The study begins with data pre-processing, including handling missing values, text transformation, and creation of a Document-Term Matrix (DTM) and TF-IDF matrix. Exploratory Data Analysis (EDA) is conducted to generate visual summaries such as word clouds and yearly trends. Advanced techniques like Topic Modelling using LDA, multiple regression analysis, classification models, association rule mining, clustering, and Principal Component Analysis (PCA) are applied. These methods reveal insights into popular research topics, predictors of citation counts, accuracy in journal classification, word associations, and abstract clustering patterns. The findings provide valuable information for researchers, journals, and academic decision-makers, highlighting trends, influential factors, and underlying structures within the academic literature.

## Data Source

This project analyzes a dataset comprising abstracts from 4385 research papers published between 2000 and 2022 across three prominent academic journals:

- [Journal of the Operational Research Society](https://www.tandfonline.com/journals/tjor20)
- [Health Systems](https://www.tandfonline.com/journals/thss20)
- [Journal of Simulation](https://www.tandfonline.com/journals/tjsm20)

Each entry in the dataset includes comprehensive details such as the paper's title, journal name, year of publication, number of pages, list of authors, number of views, number of citations, altmetric score, and the abstract. The project employs advanced data mining techniques, including text mining, topic modeling, regression analysis, classification, association rule mining, clustering, and PCA, to extract insights and patterns from this rich academic literature. The analysis aims to uncover trends, relationships, and significant themes within the research papers, providing actionable insights for researchers, journals, and academic stakeholders.

## Data Cleaning and Preparation

1. Handling Missing Values: Initially, the dataset was inspected for missing values using the `na.omit()` function in R. Rows containing null or undefined values were removed to maintain data integrity and completeness.

2. Text Data Transformation: The abstracts, a key component of the dataset, underwent extensive transformation. Text was converted to lowercase to ensure consistency, and punctuation, numbers, and common English stop words were removed to isolate meaningful terms. Unnecessary white spaces were also stripped from the text.

3. Document-Term Matrix (DTM) Creation: In text mining, the raw abstracts were structured into a Document-Term Matrix (DTM). This matrix captured the frequency of terms across documents, providing a foundational structure for subsequent analyses.

4. TF-IDF Transformation: To highlight the significance of terms within the corpus, the DTM underwent TF-IDF (Term Frequency-Inverse Document Frequency) transformation. This step emphasized terms based on their frequency within documents and their rarity across the entire dataset, ensuring that important terms stood out.

## Exploratory Data Analysis (EDA)

Visualization played a crucial role in uncovering insights from the dataset of 4385 research papers published between 2000 and 2022 across three major journals (Journal of the Operational Research Society, Health Systems, Journal of Simulation). The visualizations encompassed various techniques:

1. Word Clouds: Generated to visually represent the distribution of popular words within the abstracts, highlighting frequently occurring terms with larger and bolder fonts.

2. Yearly Trends Plots: Created to illustrate variations in metrics such as views and citations across different years, allowing identification of temporal patterns and shifts in research focus.

3. Top Terms Visualization: Plots comparing Term Frequency (TF) and TF-IDF provided insights into both raw term frequencies and their corpus-wide significance, aiding in understanding keyword relevance across the dataset.

## Topic Modelling (LDA)

### Model Description

Topic Modelling using Latent Dirichlet Allocation (LDA) is employed to uncover underlying themes within the abstracts of research papers. LDA is a probabilistic model that assumes each document is a mixture of topics, and each topic is a distribution over words. By applying LDA to our dataset, we aim to identify clusters of words that frequently co-occur in the abstracts, thereby revealing the latent topics present in the corpus.

### Optimal Topic Number Search

Determining the optimal number of topics is crucial for the effectiveness of LDA. In this analysis, we employed various metrics such as CaoJuan2009 and Deveaud2014 to find the optimal number of topics. These metrics evaluate the coherence and interpretability of topics generated by LDA. The goal is to strike a balance between having enough topics to capture distinct themes and avoiding excessive fragmentation that might dilute the interpretability.

### Visualization of Topics

Visualizing the topics extracted from LDA provides insights into the thematic structure of the dataset. We use interactive visualizations to illustrate the distribution of topics across documents, their evolution over time, and differences between journals. Each topic is represented by a set of prominent words, allowing us to interpret and label them based on their content. These visualizations facilitate a deeper understanding of the research themes explored in the abstracts and help in identifying trends or shifts in topics over the publication years.

## Regression Analysis

### Multiple Regression Model

In this project, a multiple regression model was constructed to predict the number of citations a research paper might receive based on various predictors. The predictors considered in the model include the number of views and the altmetric score of each paper. These predictors were chosen due to their potential influence on the visibility and impact of academic publications. 

### Key Predictors and Coefficients

The regression model provided insights into the relationships between the predictors and the number of citations. Key coefficients from the model indicate the direction and strength of these relationships. For instance, a positive coefficient suggests that an increase in the predictor variable is associated with an increase in citations, while a negative coefficient suggests the opposite. The analysis of coefficients helps to identify which factors, such as online views or altmetric scores, play significant roles in determining the impact and attention received by academic papers.

## Classification Analysis

### Model Overview

For the Classification Analysis, we aimed to predict the journal category of papers based on their features using machine learning models. The dataset includes abstracts from three major journals: [Journal of the Operational Research Society](https://www.tandfonline.com/journals/tjor20), [Health Systems](https://www.tandfonline.com/journals/thss20), and [Journal of Simulation](https://www.tandfonline.com/journals/tjsm20). We utilized various features such as word frequencies derived from Bag of Words (BoW) and TF-IDF matrices as input variables. 

### Accuracy Evaluation

To evaluate the accuracy of our classification models, we employed cross-validation techniques and measured metrics such as accuracy, precision, recall, and F1-score. These metrics provide insights into how well the models classify papers into their respective journals. The results of our analysis demonstrated robust performance, indicating that our models accurately predict the journal category based on the abstract content and associated metadata.

## Association Rule Mining

In this project, we utilized Association Rule Mining to uncover meaningful relationships between terms within the abstracts of academic papers. The process involved two key steps:

### Binary Matrix Transformation

Firstly, the abstract was transformed into a binary matrix format where each row represents a document (paper) and each column represents a term. The matrix entries were binary, indicating whether a particular term appeared in a specific document or not. This transformation is crucial for preparing the data for association rule mining.

### Apriori Algorithm Application

Secondly, we applied the Apriori algorithm, a classic algorithm in association rule mining, to discover frequent itemsets and derive association rules from the binary matrix. The algorithm works by identifying itemsets that meet a minimum support threshold and then generating rules based on a minimum confidence threshold. These rules provide insights into which terms frequently co-occur within the abstracts, indicating potential thematic associations or research trends.

By leveraging Association Rule Mining, we were able to extract actionable insights from the dataset, such as identifying common research methodologies, recurring themes, or collaborative topics among published papers. This analysis contributes to a deeper understanding of the underlying structure and content within the academic papers, facilitating informed decision-making for researchers and journal editors alike.

## Clustering Analysis

### Cluster Identification Method

For clustering analysis, we utilized the K-means clustering algorithm to identify distinct groups of abstracts based on similarities in their content. The algorithm partitions the dataset into clusters where each abstract is assigned to the cluster with the nearest mean, minimizing the within-cluster sum of squares. By examining clusters, we aimed to uncover underlying themes or topics that are prevalent across the dataset. The number of clusters was determined using the silhouette method to ensure robust clustering results.

## Dimensionality Reduction (PCA)

### PCA Overview

Principal Component Analysis (PCA) was employed to reduce the dimensionality of the dataset while preserving its essential structure. By transforming high-dimensional data into a lower-dimensional representation, PCA helps visualize the relationships between abstracts in a more manageable 2D space. This reduction facilitated the identification of patterns and clusters within the dataset, enhancing our understanding of the overarching themes and relationships among papers published in the Journal of the Operational Research Society, Health Systems, and the Journal of Simulation.


## Conclusion

In conclusion, this case study comprehensively analyzed a dataset encompassing 4385 research papers published between 2000 and 2022 across three prominent academic journals: the Journal of the Operational Research Society, Health Systems, and the Journal of Simulation. Through rigorous data preprocessing, advanced analytics techniques including text mining, topic modeling, regression analysis, classification, association rule mining, clustering, and PCA were applied to extract valuable insights. The findings revealed significant trends, thematic patterns, and predictive relationships within the academic literature, providing actionable information for researchers, journal editors, and academic decision-makers. This study underscores the importance of data-driven approaches in understanding scholarly publications and highlights avenues for future research and exploration in academic publishing trends.
