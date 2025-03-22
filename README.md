# Sales Opportunity Classification Model

## Project Overview

In today's competitive business landscape, sales professionals face significant challenges:

- Increasing quotas and tighter deadlines
- Complex CRM systems
- Overwhelming number of prospects with no clear conversion path

Our solution leverages a Kaggle Sales CRM dataset [https://www.kaggle.com/code/amr7ac/crm-sales-opportunities-analysis/input] to build a classification model that:

1. Identifies and tags "Won Opportunity" prospects
2. Provides sales teams with a curated list of high-conversion potential leads
3. Eliminates guesswork and random prospecting

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
- More won opportunities than lost in the sample
- Sector bias towards retail, medical, and tech/software industries

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

### Model Performance (After Hyperparameter Tuning)

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
4. Regional and sector biases in the dataset should be considered when applying the model to new data

## Next Steps and Recommendations

1. Implement the Logistic Regression or SVM model in the sales workflow
2. Continuously monitor and update the model with new data
3. Expand the dataset to include more diverse regions and sectors
4. Develop a user-friendly interface for sales professionals to access model predictions
5. Conduct regular performance reviews to assess the model's impact on sales efficiency and revenue

