# Grammar-Scoring-Engine-for-Voice-Samplesfor
🎯 Project Overview
This project is a submission for the SHL Intern Hiring Assessment, where the goal is to build a Grammar Scoring Engine that predicts a grammar proficiency score (0–5) for spoken audio samples using machine learning.

Objective: Predict a continuous grammar score from .wav audio files using audio feature extraction and regression models.

📁 Dataset
The dataset includes:

-train.csv: Filenames with corresponding label (grammar scores).

-test.csv: Filenames without labels (used for prediction).

-audios_train/: Training audio files.

-audios_test/: Testing audio files.

-sample_submission.csv: Submission format.

⚙️ Approach & Pipeline
1. 📊 Exploratory Data Analysis (EDA)
Plotted distribution of labels (grammar scores).

Visualized sample waveforms and mel spectrograms.

2. 🎵 Audio Preprocessing
Standardized all audio to fixed length (60 seconds).

Extracted meaningful features:

MFCCs (13 coefficients)

Chroma Features

Zero Crossing Rate

Spectral Centroid

3. 🧠 Model Training
Multiple regression models were tried:

Model	MAE	RMSE	Pearson Corr.
Random Forest	0.271	0.334	0.977 ✅ Best
Gradient Boosting	0.276	0.342	0.965
Ridge Regression	0.712	0.859	0.636
XGBoost (Overfit)	0.000	0.001	1.000 🚫
Others (Lasso, SVR, KNN) underperformed.			
The Random Forest Regressor provided the best balance of performance and generalization.

📈 Model Evaluation
Metrics (on train set):

Mean Absolute Error (MAE): 0.271

Root Mean Squared Error (RMSE): 0.334

Pearson Correlation Coefficient: 0.977 ✅

📊 Visualizations
✅ True vs Predicted Scores (scatter plot)

✅ Histogram of predicted scores (test set)

✅ Bar plot of sample predictions

✅ Label distribution

📤 Final Submission
The model was used to predict scores for the test.csv data, and the output was saved in:

bash
Copy
Edit
submission.csv
All predicted scores are rounded to 1 decimal place to match expected format.

💡 Interpretability
The notebook includes:

-Clear explanations of preprocessing and modeling steps.

Visual comparisons between true and predicted values.

-Score distribution plots to show prediction behavior.

-Annotated and modular code for reproducibility.

🚀 How to Run
-Clone this repo or open in Google Colab or Kaggle Notebook.

-Upload the dataset (same structure as the competition).

-Run all cells in sequence.

-Final predictions will be saved to submission.csv.

📌 Requirements
Python 3.7+, 
librosa, 
pandas, 
numpy, 
scikit-learn, 
matplotlib, 
seaborn, 
tqdm, 
