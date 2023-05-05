# Heart Failure Readmission Predictor
This is a machine learning project that aims to predict hospital readmissions for heart failure patients. The prediction is made using both general readmission data and 30-day readmission data. The project uses a Convolutional Neural Network (CNN) model for the prediction.

# Dependencies
This project depends on several Python libraries including:

pandas
numpy
nltk
gensim
tensorflow
sklearn
random
datetime

# Dataset
The dataset used in this project is hospital admissions data, specifically:

ADMISSIONS.csv
NOTEEVENTS.csv
DIAGNOSES_ICD.csv
These files contain information about patient admissions, notes from healthcare providers, and ICD-9 codes for diagnoses.

# Pre-processing
The data is pre-processed by filtering for heart failure admissions based on specific ICD-9 codes. Discharge summaries are also filtered and the longest one for each admission is kept. Admissions are labeled based on whether they resulted in a general readmission or a 30-day readmission.

The text from the notes is also preprocessed by tokenizing, removing stopwords and non-alphabetic tokens, and re-joining all tokens into the text.

# Model
A Convolutional Neural Network (CNN) model is used for predicting readmissions. The model uses an Embedding layer with pre-trained word vectors from PubMed, followed by Convolutional and MaxPooling layers. The Dense layers include dropout for regularization. The model is compiled with the Adam optimizer and binary crossentropy loss function.

The model is trained using 10-fold cross-validation on the training data, with learning rate reduction and early stopping callbacks.

# Evaluation
The model's performance is evaluated using precision, recall, F1 score, and accuracy on the validation data for each fold of cross-validation. The mean values of these metrics are reported for both general and 30-day readmissions.

# Usage
To use this project, you should have the required dependencies installed. The paths to the data files and the pre-trained word vectors need to be specified correctly in the code.

Please note that due to the use of random seed, the results could vary slightly each time the program is run. However, the overall trend and performance should remain consistent.

# License
This project is open-source and available to anyone for personal or research purposes. Please ensure to give credit if you use the code or data.
