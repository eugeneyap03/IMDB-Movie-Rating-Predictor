# IMDB-Movie-Rating-Predictor

The goal of this project is to build and critically analyse supervised machine learning methods for predicting IMDB movie ratings based on various predictor variables that include movie-title, duration, director and actor(s) names and facebook likes, keywords, genre, country, budget, and others. There are five possible outcomes 0 being the lowest and 4 being the highest.

The movie dataset is derived from the [IMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/carolzhangdc/imdb-5000-movie-dataset "IMDB 5000 Movie Dataset").

A report was also written as a critical analysis for the models created.

## JUPTYER NOTEBOOK README

### Additional Data Preprocessing
The train and test dataset is further processed before exported as new
data files:
- The 'genres' and 'plot_keyword' columns are cleaned by removing '|' and
splitting the values into lists.
- Removed rows with no genres or no plot_keywords for train data
- These respective columns are label encoded to prepare the data for analysis.
- Features that contain numerical values that have a greater range of 10000.
- These selected features underwent normalisation.

### Exploratory Data Analysis 

In this section, we perform exploratory data analysis (EDA) on the IMDb
scores of the dataset. The following actions are taken:

**Media Count vs IMDB Score:**
Created a visual representation on the distribution of IMDB Score in the Dataset.
**Feature Correlation Heatmap:**
Created an additional feature visual representation to select features that have strong correlations with each other.
 
### Model 1: Classification Using k-Nearest Neighbors (KNN)
KNN classification is applied to predict binned IMDb scores.
**K and Feature Selection:**
- Applied SelectKBest with ANOVA F-test to select 4 best features.
- K-value that provided the highest mean accuracy was selected.
**Cross Validation:**
- A 5-fold stratified cross-validation is applied to estimate the average accuracy, precision, recall, and F1 score.
- This helps assess the model's performance and compare it to a baseline model (Zero-R).

### Model 2: Classification using Bagging
A Bagging Classifier using a Decision Tree-based classifier is used to predict IMDb score bins.
**Feature Selection:**
- Only normalised features were used
**Performance Metrics:**
- Model accuracy, precision, recall, and F1 score are evaluated.
- A confusion matrix is visualized to assess classification performance.
