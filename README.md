# Netflix-Movie-and-Series-Rating-Category-Classification 

OBJECTIVE:
      The goal of this project is to build a machine learning classification model that predicts the rating category of Netflix movies and series. The target variable, rating_category, classifies content into categories like Family-friendly,Teen/Young Adult, Adult based on various features of the dataset such as Movies/series(types), Movie released year, Netflix uploaded year, country, duration, Movie/Series Title and Directors. In this Movie released year and Netflix uploaded year features are converted into Content Age and Movie Age for better prediction of model.

Problem Statement:
      With an increasing variety of content available on streaming platforms like Netflix, classifying content based on its appropriate audience rating is essential. This classification model helps to enhance content filtering and recommendations, ensuring that viewers can easily find content suited to their age or preferences.

Scope: The dataset contains information about Netflix movies and series, such as  release year, cast,duration,genres and more, which will be used to classify them into appropriate rating categories.

Limitations: The project is limited to publicly available datasets and may not include every potential feature that could influence content rating.

STEPS:

1) DATA COLLECTION:
   
           i)DATA SOURCE: The data was collected from  Kaggle Netflix datasets . The dataset includes various attributes of Netflix movies and series.
   
           ii)DATA DESCRIPTION: Initially contains features like types(movies/series),Title, Director, Cast, Country(Origin of Movie), date added, release year,description, genre, duration etc.In this I have taken Rating category as Target.

2) DATA CLEANING AND PREPROCESSING:
   
             i)HANDLING MISSING VALUES: Due to majority of categorical columns we use approaches like mode imputation and also filled the missing values with  "unknown".The Tool used widely in handling missing values is Pandas.

             ii)TARGET INITIATION: I categorised Rating Category into three classes, which initially has many categories representing same classes and made that as target. To avoid class imbalance, and to maintain balance, class like "uncategorised" with least no of rows in entire dataset is removed.It has only 1% in entire dataset and that is the main reason for removal.

             iii)FEATURE ENGINEERING: Created New Features like Movie Age and Content Age from already existed features like Release date and date added to netflix.Removed unnecessary features like Description, Listedin, cast, show id etc, which is considered as less important.Features like Duration is categorised as very short, medium, long, very long, epic for better model performance.Country and Directors are also categorised for less unique values in particular features.In this Movie title is converted into Title_words using lamba function(by splitting the words and considering its length). This is mainly done to better understanding for model. Sometimes long title words movies mainly come under one genre and short title words comes under one genre. 

             iv)DATA TRANSFORMATION: Mainly focused on label encoding for majority of columns. and performed Standard scalar on Movie age feature.

3) Exploratory Data Analysis (EDA)

               i)DATA VISUALIZATION: In this dataset, majority of them are Categorical columns so performed bar plot, stacked bar plot etc. Performed Univariate & Bivariate analysis for respective features. In this Many plots are done by comparing features with target variable(rating category)

               ii)CORRELATION ANALYSIS: Heatmap is not necessary for Categorical columns, here i performed is just for just showing the relationship between variables

               iii)FEATURE IMPORTANCE:Here i performed RandomForestClassifier, and find out the important features.It is concluded that movie_age, country_category, Duration_category, Content_Age, Title_words are top 5 features that make huge influence on rating category(target) for audiences.

4)MODEL DEVELOPMENT:

                i)MODEL SELECTION: Here target is multi classification, so i selected models such as KNN, Decision tree, Random Forest, Support Vector Machine and XG Boost. Main reason for this model selection that they can handle non linear models and can handle large datsets.

                ii)MODEL SPLIT: Dataset is usually split by train test split as 80/30 or 80/20 in these cases. 

                iii)MODEL TRAINING: First done trial and error method to choose Best  hyperparameter for ecah and every model. After Hyperparameter selection it is trained in models. 

5)MODEL EVALUATION:

                  i) EVALUATION METRICS: Accuracy for Overall performance of the model. Precision, Recall, F1-Score for Metrics to understand how well the model handles each class, especially for imbalanced data.Confusion Matrix for Display confusion matrices for each model to assess how well they perform across different rating categories.This Evaluation metrics are done for each and every model to comapre and choose the best model.

                  ii)MODEL COMPARISON: XGBoost appears to be the best performing model overall, considering that it has the highest accuracy and is competitive across precision, recall, and F1-score.Random Forest and Decision Tree also perform well but lag slightly behind XGBoost in terms of accuracy and F1-score.KNN and SVM have lower performance overall, with SVM particularly struggling in recall and F1-score.

                  iii)BEST MODEL: XGBoost stands out as the best performing model for this classification task 

6)CONCLUSION: 

                  i)SUMMARY OF RESULTS:The XG Boost classifier performed better than other models with the good accuracy of 60%, when compare to another models.The model can predict the rating category of Netflix content with a reasonable degree of accuracy. 

                  ii)LIMITATIONS:The challenges faced in this project are:If certain features (e.g., user reviews or plot summaries) could have improved the classification model accuracy, but they weren't included in the dataset. If some categories had fewer samples, it might affect model performance. 

                  iii)FUTURE WORK:IMPROVEMENT AREAS:Incorporating additional features like user ratings or plot details.Testing other advanced models (e.g., deep learning or neural networks) for better performance.
 
 
 


         
   
                     













    
