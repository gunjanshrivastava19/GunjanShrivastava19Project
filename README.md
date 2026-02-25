**Spam Detection Project**
This project is a machine learning-based Spam Detection System that classifies SMS messages as Spam or Not Spam (Ham). It uses text preprocessing, TF-IDF feature extraction, and a Logistic Regression model to make predictions. The system also includes a keyword-based check for detecting obvious spam messages.

**What the Project is Doing**
The project loads a dataset of SMS messages and trains a model to learn patterns that differentiate spam from normal messages. It first cleans the text by converting it to lowercase and removing special characters. Then, it converts the text into numerical features using TF-IDF (including single words and word pairs). A Logistic Regression model is trained on this processed data.

**During prediction, when a user enters a message, the system:**
1. Checks if it contains strong spam keywords like “lottery” or “free”.
2. If not, it uses the trained model to calculate the probability of the message being spam.
3. Based on the probability threshold (0.35), it classifies the message and shows the confidence score.

In short, the project builds a real-time spam classifier that combines rule-based detection and machine learning for better accuracy.

**Code Explanation**
This project builds a Spam Detection System using Machine Learning and a small rule-based filter. Below is the explanation of how the code works:

**1. Importing Libraries**

The required libraries are imported:
1.pandas for handling the dataset
2.re for text cleaning using regular expressions
3.train_test_split for splitting data
4.TfidfVectorizer for converting text into numerical features
5.LogisticRegression for building the classification model

**2. Loading and Preparing the Dataset**

1.The dataset spam.csv is loaded using pandas.
2.Only the relevant columns (v1, v2) are selected.
3.Columns are renamed to label and message.
4.Missing values are removed.
5.Labels are converted into numeric form:
ham → 0
spam → 1
This prepares the data for training the model.

**3. Text Cleaning**

1.A function clean_text() is created to preprocess the messages:
2.Converts text to lowercase.
3.Removes numbers and special characters.
4.Keeps only alphabets and spaces.
5.All messages in the dataset are cleaned using this function.

**4. Splitting the Data**

1.The dataset is split into:
**80% Training Data
20% Testing Data**
2.Stratified splitting ensures equal distribution of spam and ham messages in both sets.

**5. Feature Extraction using TF-IDF**

The TfidfVectorizer converts text messages into numerical vectors.
1.ngram_range=(1,2) means the model considers:
2.Single words (unigrams)
3.Two-word combinations (bigrams)
This helps the model understand important word patterns like “free cash”.

**6. Model Training**
1.A Logistic Regression model is created and trained using the vectorized training data.
2.The model learns patterns that distinguish spam messages from normal messages.

**7. Strong Keyword Detection**
A list of strong spam keywords is defined:
**lottery
prize
winner
claim
free
cash**
If any of these words appear in a message, it is directly classified as spam without using the model.

**8. Real-Time Prediction**

The program runs in a loop and:
1.Takes user input.
2.Stops if the user types exit.
3.Cleans the input message.
4.Checks for strong spam keywords.
5.If no keyword is found:
**Converts the message into TF-IDF format.
Predicts spam probability using the trained model.**
6.If probability > 0.35 → Classified as **SPAM**
Otherwise → **NOT SPAM**
7.Displays the confidence score.

<img width="1089" height="811" alt="image" src="https://github.com/user-attachments/assets/99d57cff-319a-4449-930f-57a443961bd1" />
<img width="1128" height="277" alt="Screenshot 2026-02-25 194027" src="https://github.com/user-attachments/assets/5b3d7b82-a576-49ab-a3d5-699055b0b9cf" />
<img width="1029" height="286" alt="Screenshot 2026-02-25 194645" src="https://github.com/user-attachments/assets/214cc507-94f5-4676-9ba7-fdba968e0e05" />


