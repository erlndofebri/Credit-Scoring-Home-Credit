# Credit Scoring Using Logistic Regression
As a data science intern at Home Credit, I was assigned to make a credit risk analysis and credit scoring. My objective here is to make a good prediction model that can classify whether the clients are having payment difficulties or not.
I used logistic regression as a model to predict credit risk and implemented weight evidence & information values to perform feature selection. Metrics used in this project are ROC-AUC score and KS-Statistic. My goals here are: 

1. build a prediction model with good ROC-AUC score (>0.7) and good KS-Statistic score (>0.3)
2. build credit score (score card) each borrower and treshold ecommendation list


Metrics used in this project are ROC-AUC score and KS-Statistic

## Dataset Overview
1. This datasets is about client application record for credit loans
2. The dataset consists of 121 features and  0.37 million records training dataset and 120 features  + 38k record testing dataset
3. There are 50 features containing >20% missing values, we dropped it and did missing values imputation for the rest features
4. The target feature is labelled as client's payment difficulties, 1 stands for the client with payment difficulties.
5. Target feature is highly imbalanced (91:9), we handled with SMOTE technique
6. We only used training application dataset for modeling , we will only use additional dataset for gaining insights

## Feature Engineering and Feature Selection
1. Data preprocessing: dropped unused features, missing values imputation, datetime feature engineering, and feature encoding
2. Feature Selection: using Weight of Evidence and Information Values
3. Feature encoding and feature binning
4. Split for training and testing
5. Handling imbalanced target feature
6. We got 79 features ready to be training in machine learning model


## Modeling
We used  logistic regression to predict whether the borrower will be a good  borrower or not.  We also used AUC score and KS-Statistic as our evaluation metric. After performing hyperparameter tuning and feature selection, the results are :
1. AUC Training Score : 0.72
2. AUC Testing Score : 0.72
3. KS Statistic : 0.33


![Credit Scoring](https://user-images.githubusercontent.com/106853320/193282353-f27f8a79-d630-49bd-b209-59c3b6e4f522.png)


## Feature Importance:
1. Male borrowers have higher odds of being a borrowers with payment difficulties 1.003 times than female
2. Borrowers who live in population relative 4 have higher odds of being a borrowers with payment difficulties 1 times than other area
3. Borrowers who have a car have higher odds of being a borrowers with payment difficulties 0.95 times than borrowers with no car
4. Borrowers who have no children have higher odds of being a borrowers with payment difficulties 0.93 than other CNT_FAM_MEMBER
5. Borrowers with 4 or more children have higher odds of being a borrowers with payment difficulties 0.92 than other CNT_FAM_MEMBER

## Credit Score Card:

![Screen Shot 2022-09-30 at 20 42 45](https://user-images.githubusercontent.com/106853320/193282937-317ddab2-6549-4a04-bc62-a56b30a43262.png)


full credit score file: [Download](https://drive.google.com/file/d/1GwSy7xZ6YO2vN4T2MjuecZ-kT0yiJ7-s/view?usp=sharing)

![Screen Shot 2022-09-30 at 20 42 51](https://user-images.githubusercontent.com/106853320/193283044-8b9804d0-609c-44d2-a54e-a5e3e1187909.png)

full credit score file: [Download](https://drive.google.com/file/d/12BblBWnY6-GVSEY3oPpuiKvKTZDQBXQH/view?usp=sharing)

## Insights:

![figure13](https://user-images.githubusercontent.com/106853320/193283204-fd5454ae-398a-41ed-bb0b-6bf8470e9b95.png)
1. Gender and Car Ownership  are the top 3 important features, demographically male with care ownership have a higher probability to be clients with payment difficulties
2. We suggest marketing department to target  female clients and/or male prospective clients with no car ownership and personalized campaign with demographic information related to next recommendation

![figure11](https://user-images.githubusercontent.com/106853320/193283288-e3df83a2-4670-486b-b0a8-270039ebf71e.png)
1. Client with no children and  have >4 children  are the top 6 important features
2. Our recommendation in marketing department, focus on client with less children and aware with client that have either no children or too many children
3. It's make sense when family with no burdency and with too many burdency to have payment difficulties

![figure12](https://user-images.githubusercontent.com/106853320/193283364-528ca779-c510-46cb-8a5e-b6af9ec80d58.png)
1. Client with amount price for loans < 300k and >900k are top 10 feature importance
2. Our recommendation in marketing department, between those range because it has lower probability to have payment difficulties
3. Company should aware with too little amount goods price and/or with too high amount goods of price. 


