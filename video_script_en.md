# Five-Minute Presentation Script

Record the screen while the executed notebook is open. Scroll through the relevant cells and point to the code and outputs while speaking. There is no need to read every line of code.

## 0:00-0:25 - Introduction

"Hello, I am Maor C. For this assignment I selected text analysis and a supervised multiclass classification problem. I used the Emotions dataset for NLP from Kaggle. The objective is to receive an English sentence and predict its emotion. I trained a multiclass Logistic Regression classifier using the ready-made implementation from scikit-learn."

Show the notebook title, assignment type, algorithm, and dataset link.

## 0:25-0:55 - Dataset and Learning Problem

"The dataset contains 20,000 sentences and six classes: anger, fear, joy, love, sadness, and surprise. It is already divided into 16,000 Train samples, 2,000 Validation samples, and 2,000 Test samples, so I did not split any file again. Validation is used for hyperparameter selection, and Test is reserved for the final evaluation."

Show the split sizes and the first five rows of Train and Test.

## 0:55-1:25 - Exploratory Analysis and Metric

"I checked missing values, duplicates, and unexpected labels. The class-distribution plot shows that the dataset is imbalanced: joy and sadness are large classes, while surprise is small. Therefore, the primary evaluation metric is Macro-F1. It calculates F1 for every emotion and averages the class scores equally."

Show the data-quality table, class counts, and plots.

## 1:25-2:05 - Feature Engineering

"The text is converted to lowercase, URLs and user mentions are replaced with fixed tokens, and irrelevant characters are removed. I then use TF-IDF. Term Frequency measures the importance of a word in a sentence, while Inverse Document Frequency reduces the weight of words that occur throughout the corpus. The vectorizer is fitted on Train only. Validation and Test use transform only, preventing data leakage."

Show the three Train examples and three Test examples after feature engineering.

## 2:05-2:50 - Learning Algorithm

"The model is Logistic Regression from scikit-learn. For each TF-IDF vector, the model calculates a linear score for every emotion. In multiclass classification, Softmax converts these scores into probabilities that sum to one. The model minimizes cross-entropy loss and applies L2 regularization."

"The important hyperparameters are C, class weight, maximum iterations, and the optimization solver. A larger C means weaker regularization. Balanced class weights give more importance to rare emotions. The estimator provides fit, predict, and predict-proba methods."

Show the explanation and the `LogisticRegression` construction.

## 2:50-3:35 - Hyperparameter Experiments

"I tested four combinations on Validation only: a baseline without class weights, balanced weights with C equal to one, balanced weights with C equal to four, and a version that includes both unigrams and bigrams. The results show that balanced class weights improve Macro-F1. C equal to four performs best, while bigrams do not improve the score in this dataset."

Show the experiment table, validation plot, and selected configuration.

## 3:35-4:25 - Final Training and Test Results

"After selecting the hyperparameters, I fitted a new vectorizer and classifier on Train and Validation together, using 18,000 examples. I then evaluated the model once on Test. The first five predictions are shown here. The final result is approximately 0.84 Macro-F1 and 0.89 Accuracy. Macro-F1 remains the primary result."

"The confusion matrix and classification report show strong performance for sadness, joy, and anger. Surprise and love are more difficult because they have fewer examples and share vocabulary with other emotions."

Show the five predictions, final scores, report, confusion matrix, and per-class F1 chart.

## 4:25-5:00 - Interpretation, Limitations, and Conclusion

"Because Logistic Regression is interpretable, I can display the terms with the largest positive coefficient for every emotion. I also examined several high-confidence mistakes. TF-IDF mainly identifies word occurrence and does not fully understand context, irony, or complex word order. A recurrent neural network or Transformer could model context better, but would require a more complex training process. Finally, I added a function that predicts the emotion and class probabilities of any new sentence. Thank you."

Show the top-word table, error examples, and the new-text prediction function.

## Questions to Prepare For

- Why was the dataset not split again? Kaggle already provides Train, Validation, and Test files, and the assignment requires preserving them.
- Why use Macro-F1? It gives equal importance to every emotion in an imbalanced multiclass problem.
- Why must TF-IDF not be fitted on Test? Fitting on Test would leak vocabulary and frequency information into training.
- What does Softmax do? It converts class scores into probabilities that sum to one.
- What does the `C` parameter control? It is the inverse of regularization strength; larger values apply weaker regularization.
- Why use balanced class weights? They increase the influence of rare classes during optimization.
- Why did bigrams not help? They increased the feature space and added many relatively rare combinations without improving generalization.
- What is the difference between Validation and Test? Validation selects hyperparameters; Test provides the final unbiased evaluation.

