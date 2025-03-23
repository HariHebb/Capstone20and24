# Sales Opportunity Classification Model

## Project Overview

In today's competitive business landscape, sales professionals face significant challenges:

- Increasing quotas and tighter deadlines
- Complex CRM systems
- Overwhelming number of prospects with no clear conversion path
- A lot of time spent nurturing low propensity customers who would not convert, thus impacting their ability to meet their quotas and forecasts

Our solution leverages a Kaggle Sales CRM dataset [https://www.kaggle.com/code/amr7ac/crm-sales-opportunities-analysis/input] to build a classification model that:

1. Identifies and tags "Won" Opportunities
2. Provides sales teams with a curated list of high-conversion potential leads
3. Eliminates guesswork and random prospecting
4. Helps Sales folks focus on the opportunities which have higher propensity to convert into a deal

## Key Links

- Link to the python notebook [https://github.com/HariHebb/Capstone20and24/blob/main/Capstone_EDA_Plus_Model.ipynb]
- **Link to the document with detailed analysis which help arrive at the concise documentation [https://docs.google.com/document/d/1CFRjP5TzvYRQmJQ6p6OdyZIz7oDy6VbXJYdO_nReqRI/edit?tab=t.0]**
- Link to git  [https://github.com/HariHebb/Capstone20and24.git]

## Dataset Description

The dataset contains information from a fictional company's CRM system, including:

1. Account.csv: Company information
2. Products.csv: Product and price details
3. sales_pipeline.csv: Opportunity information
4. sales_team.csv: Sales team data

## Exploratory Data Analysis (EDA)

Key observations:

- 85 customers, 7 products, 35 sales team members
- 8800 opportunities in the sales pipeline
- Regional bias towards US customer data (>85%)
  ![image](https://github.com/user-attachments/assets/6523c048-a7e8-4729-a8ff-cb83e6eed2cd)
- More won opportunities than lost in the sample

![image](https://github.com/user-attachments/assets/f172682e-60bf-4b33-8317-ddef9532b659)

- Sector bias towards retail, medical, and tech/software industries
![image](https://github.com/user-attachments/assets/a29bfacd-4527-4a83-9909-b22252397b8c)
- No strong correlation between numerical variables and the target variable . Value and days deal opened have the highest values with 0.49 and 0.12

![image](https://github.com/user-attachments/assets/b9f53a9c-3439-4d39-93ca-d7ab7e0f58c9)
- Low frequency of GTK series in the dataset

![image](https://github.com/user-attachments/assets/eab851ec-a0df-45c2-b7db-5ef66f906922)
![image](https://github.com/user-attachments/assets/d3ffc641-32fb-46d5-8d0f-d0ccad7edd97)



## Data Preprocessing

- Filtered irrelevant data and removed in-flight opportunities
- Created a column for opportunity duration
- Denormalized data across multiple tables
- Applied standard scaling for numerical columns and one-hot encoding for categorical columns

## Modeling

Multiple classification models were developed and evaluated:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree
4. Support Vector Machine (SVM)
  


### Cross-validation and Hyperparameter Tuning

- Used cross-validation to assess model performance and detect overfitting
- Employed Grid Search for hyperparameter tuning to optimize model performance

### Evaluation Metrics

Primary metrics used: accuracy, precision, recall, and F1 score

Rationale: These metrics provide a comprehensive view of model performance, balancing the ability to correctly identify both positive and negative cases.

### Model Performance (Before Hyperparameter Tuning)
 
 The plots showing the performance of the model before hyperparameter tuning

![image](https://github.com/user-attachments/assets/4e69a683-0b3f-4e1c-b694-f38bae8edc3d)

- KNN is fastest (0.033s), while SVM is slowest (1.936s); Decision Tree achieves 100% accuracy but may be overfitting
- All models show identical Precision (92.42%) and Recall (99.19%), with an F1 Score of 95.69%, indicating strong and balanced performance.
- Logistic Regression offers a good balance of speed (94.49% test accuracy) and performance, making it a practical choice alongside KNN for this use case.

### Model Performance (After Hyperparameter Tuning)

 The plots showing the performance of the model after hyperparameter tuning 


![image](https://github.com/user-attachments/assets/154c70eb-0e79-4514-a7c7-0b460267abdf)


- KNN: Fastest (1.5 seconds), lowest precision (80.9%) and recall (88.3%)
- Decision Tree: 100% accuracy (likely overfitting)
- Logistic Regression: Slowest (112 seconds), 98.96% accuracy
- SVM: Excellent accuracy (99.65%) with strong generalization

### Model Interpretation

- Logistic Regression and SVM provide the best balance of speed, accuracy, and generalization
- Decision Tree model should be avoided due to potential overfitting
- KNN is suitable only for simple or small datasets where speed is critical

## Findings

1. The classification model successfully identifies high-potential sales opportunities
2. Logistic Regression and SVM models offer the best performance for this dataset
3. The model can significantly improve sales efficiency by prioritizing leads with higher conversion likelihood
4. Regional, sector & product series biases in the dataset should be considered when applying the model to new data

## Next Steps and Recommendations

1. Implement the Logistic Regression or SVM model in the sales workflow
2. Continuously monitor and update the model with new data
3. Expand the dataset to include more diverse regions and sectors
4. Develop a user-friendly interface for sales professionals to access model predictions
5. Conduct regular performance reviews to assess the model's impact on sales efficiency and revenue

