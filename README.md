# What opportunities exist to increase reading and math proficiencies among students in the United States by identifying and analyzing factors contributing to low scores? 
![Header](https://epe.brightspotcdn.com/dims4/default/482d59d/2147483647/strip/true/crop/1690x1147+15+0/resize/840x570!/quality/90/?url=https%3A%2F%2Fepe-brightspot.s3.us-east-1.amazonaws.com%2F8b%2F86%2Fe8fb87bc41f1a1bdb4126f382d56%2Fannenberg-brown-principal-impact-08222022-1354857551.jpg)
## 1. Introduction [Problem Statement](https://github.com/ToniRene/Capstone-Two/blob/main/1.%20Capstone_Two_Problem_Statement_Worksheet.pptx.pdf)
- **Objective:** The goal of this project is to analyze educational performance data across various jurisdictions. The primary focus is to explore patterns in math and reading scores and understand how demographic features such as ethnicity, socio-economic status, and gender influence these scores.
- **Scope:** The analysis involves unsupervised learning techniques, primarily clustering, to identify patterns and relationships within the data.
## 2. Data Overview
- **[Data Source](https://github.com/ToniRene/Capstone-Two/blob/main/joined_df_cleaned.csv):** The data consists of educational performance metrics from various jurisdictions. The features include average math and reading scores, as well as demographic information such as ethnicity (White, Black, Hispanic), English Language Learners (ELL), socio-economic status (Low SES), gender (Male, Female), and Exceptional Student Education (ESE).
- **Data Description:**
  - **Math Scores:** The dataset includes Average Math Score for each jurisdiction.
  - **Reading Scores:** Similarly, Average Reading Score is provided.
  - **Demographics:** The features ELL_x, White_x, Black_x, Hispanic_x, Low SES_x, Male_x, Female_x, and ESE_x relate to math scores, while ELL_y, White_y, Black_y, Hispanic_y, Low SES_y, Male_y, Female_y, and ESE_y relate to reading scores.
![Data](https://github.com/ToniRene/Capstone-Two/raw/main/Screenshot%202024-08-25%20at%201.31.55%20PM.png)
## 3. Methodology 
- **Data Preprocessing:** The data was cleaned and preprocessed to handle any missing values, ensuring it was ready for analysis.
- [EDA](https://github.com/ToniRene/Capstone-Two/blob/main/3.%20Capstone_Two_EDA.ipynb)
- **Feature Scaling:** Features were scaled to ensure that no single feature dominated the clustering process.
- **Clustering Techniques:**
  - K-means Clustering: Applied K-means with different numbers of clusters (2 to 6) to both math and reading features. The silhouette scores helped determine the optimal number of clusters.
  - Hierarchical Clustering: Used Ward's method for hierarchical clustering and generated dendrograms for visual inspection.
- **Dimensionality Reduction:**
  - PCA: Reduced dimensions to 2 components for visualization.
  - t-SNE: Further reduced dimensions for a more non-linear separation of clusters.
- **Predictive Modeling**
  - Generated synthetic data and used predictive modeling to predict the math and reading scores of a student based on demographic factors.
  - Gradient Boosting Regressor was selected for both math and reading predictions due to its ability to handle complex, non-linear relationships.
  - 50 estimators, a learning rate of 0.01, and a max depth of 3 were used to prevent overfitting.
  - [Modeling Notebook](https://github.com/ToniRene/Capstone-Two/blob/main/5.%20Modeling_Unsupervised.ipynb)
## 4. Results
- **Optimal Number of Clusters:**
  - For Math Scores, the optimal number of clusters is 2, with the highest silhouette score of 0.2758.
  - For Reading Scores, the optimal number of clusters is 3, with the highest silhouette score of 0.2403.
- **Cluster Characteristics for Math Scores:**
  - Cluster 0: Contains students with lower values in socio-demographic features such as ELL status, race/ethnicity, SES, and gender. These students also have a lower average math score.
  - Cluster 1: Includes students with higher values in these features, reflecting a generally higher socio-economic status and better performance in math scores.
- **Cluster Characteristics for Reading Scores:**
  - Cluster 0: Represents students with higher values across socio-demographic features, including ELL status, race/ethnicity, and SES, along with a higher average math score.
  - Cluster 1: Shows mixed socio-demographic characteristics, with an average math score similar to Cluster 0.
  - Cluster 2: Includes students with the lowest values in socio-demographic features and the lowest average math score.
- **Performance Trends:**
  - In both math and reading, higher socio-economic status and better demographic characteristics are associated with higher average scores.
  - The clusters with higher average math and reading scores correspond to higher values in socio-demographic features, while those with lower scores are associated with lower values.
- **Insights for Targeted Interventions:**
  - Cluster 0 (for both Math and Reading) may benefit from targeted interventions to improve performance, given its lower average scores and socio-demographic challenges.
  - Cluster 1 and Cluster 2 (Reading) have higher average scores but might still need support in maintaining performance and addressing specific challenges.
-**Predictive Modeling Results:**
    - Math Model: Predicted Math Score (Original Scale): 234.85
    - Reading Model: Predicted Reading Score (Original Scale): 216.95

## 5. Insights
  - There is a moderate positive correlation between the Average Math Score and White ethnicity (White_x, White_y), indicating that jurisdictions with higher proportions of White students tend to have higher math scores.
  - There is a moderate positive correlation between the Average Math Score and Low Socioeconomic Status (Low SES_x, Low SES_y), indicating that jurisdictions with higher proportions of students from low socioeconomic backgrounds tend to have slightly lower math scores.
  - There is a moderate positive correlation between the Average Math Score and Male students (Male_x, Male_y), indicating that jurisdictions with higher proportions of male students tend to have slightly higher math scores.
  - There is a moderate positive correlation between the Average Reading Score and White ethnicity (White_x, White_y), indicating that jurisdictions with higher proportions of White students tend to have higher reading scores.
  - There is a moderate positive correlation between the Average Reading Score and Low Socioeconomic Status (Low SES_x, Low SES_y), indicating that jurisdictions with higher proportions of students from low socioeconomic backgrounds tend to have slightly lower reading scores.
  - There is a moderate positive correlation between the Average Reading Score and Female students (Female_x, Female_y), indicating that jurisdictions with higher proportions of female students tend to have slightly higher reading scores.
![Scatterplot of Scores by Jurisdiction](https://github.com/ToniRene/Capstone-Two/raw/main/Screenshot%202024-08-25%20at%201.31.34%20PM.png)
![Math & Gender](https://github.com/ToniRene/Capstone-Two/raw/main/Screenshot%202024-08-25%20at%201.32.50%20PM.png)
![Reading & Gender](https://github.com/ToniRene/Capstone-Two/raw/main/Screenshot%202024-08-25%20at%201.32.56%20PM.png)

- **Challenges:**
- Data limitations, such as missing values in some jurisdictions.
- The difficulty in capturing the complete picture using unsupervised methods alone.
## 6. Conclusion
- These findings suggest that socio-demographic factors have a significant impact on student performance, and interventions may need to be tailored according to the characteristics of each cluster to effectively support all students.

## 7. Recommendations
Further Research: Propose further research to delve deeper into specific clusters or to explore the impact of interventions.
Policy Recommendations: Offer actionable recommendations for policymakers, such as targeted support for ELL students or increased funding for schools in low SES areas as well as early support for female students in math and male students in reading. 
