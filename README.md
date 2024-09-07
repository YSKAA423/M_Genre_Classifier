# Music Classification Project - Shai for AI (Group D) (Kaggle-Competition)[Kaggle Competition URL Placeholder](https://www.kaggle.com/competitions/music-genre-classification-2024/overview]

## Overview
This project, part of Shai for AI's Machine Learning Internship, namely the classification task kaggle competition, as part of Group D. It focuses on classifying songs based on various audio features like danceability, energy, loudness, and more, using machine learning models. The dataset contains both numeric and categorical features, and the task involves predicting the class (popularity level) of the songs.

## Dataset
The dataset includes the following features:

- **Artist Name**: The name of the artist who performed the track.
- **Popularity**: The popularity score of the song.
- **Danceability**: The measure of how suitable a track is for dancing.
- **Energy**: The intensity and activity level of the track.
- **Key**: The key of the track (expressed as an integer).
- **Loudness**: The overall loudness of the track.
- **Mode**: Modality of the track (0 for minor and 1 for major).
- **Speechiness**: The presence of spoken words in the track.
- **Acousticness**: A confidence measure of whether the track is acoustic.
- **Instrumentalness**: Whether the track contains no vocals.
- **Liveness**: Detects the presence of a live audience.
- **Valence**: The musical positivity conveyed by a track.
- **Tempo**: The speed of the track.
- **Duration in Min/MS**: The duration of the track in milliseconds.
- **Time Signature**: The overall time signature of the track.
- **Class**: The target class to predict, representing popularity levels (0-10).

## Data Cleaning
- Missing values were found in the **Popularity**, **Key**, and **Instrumentalness** columns. These were filled with the median of each respective column.
- The **Track Name** column was removed as it is not useful for prediction.

## Data Preprocessing
- Boxplots and histograms were generated to understand the distribution of numeric features.
- Correlations between numeric features were visualized using a heatmap.
- Categorical features like **Artist Name** were handled using the **CatBoostClassifier**, which efficiently deals with categorical variables.

## Visualization
- Histograms were created to observe the distributions of numeric features.
- Boxplots were used to identify outliers and understand the spread of data for key features.
- A correlation heatmap was generated to analyze the relationships between numeric features.

## Modeling
The following models were trained and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- CatBoostClassifier

The **CatBoostClassifier** was chosen as the primary model due to its ability to handle categorical data efficiently and its fast training times.

## Model Training
- The dataset was split into training and testing sets with an 80-20 ratio.
- The target variable was **Class**, representing different levels of popularity.
- The **CatBoostClassifier** was configured with the following parameters:
  - Iterations: 100
  - Depth: 6
  - Learning Rate: 0.1
  - Cat Features: Artist Name
  - One Hot Max Size: 25

## Model Evaluation
- The model was evaluated using the F1 Score (macro), which balances precision and recall across multiple classes.
- The F1 score achieved on the test set was 0.667.

## Requirements
To run this project, you'll need the following Python libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `CatBoost`

You can install the required libraries using pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn catboost
```

## How to Run the Code

This section outlines the steps to execute the music classification script:

1. **Preprocess the Dataset:**
   - Handle missing values.
   - Drop irrelevant columns (e.g., Track Name).

2. **Split the Dataset:**
   - Divide the data into training and testing sets.

3. **Train the CatBoostClassifier:**
   - Train the model using the CatBoost library on the training data.

4. **Evaluate the Model:**
   - Assess the model's performance on the test data using the F1 Score.

**To run the script:**

1. Open a terminal window.
2. Navigate to the directory containing the `music_classification.py` script.
3. Execute the following command:

```bash
python music_classification.py
```
**Conclusion**

This project demonstrates the application of machine learning for classifying songs based on various audio and metadata features. The CatBoostClassifier was employed as the primary model and achieved a satisfactory performance. Future improvements can be explored through hyperparameter tuning and experimentation with alternative models.
