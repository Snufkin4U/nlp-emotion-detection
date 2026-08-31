# Machine Learning Assignment - Emotion Recognition from Text

This project presents a complete NLP workflow for classifying English sentences into six emotion categories: `anger`, `fear`, `joy`, `love`, `sadness`, and `surprise`.

The notebook includes dataset loading, exploratory data analysis, text cleaning, TF-IDF feature engineering, a ready-made scikit-learn Logistic Regression classifier, hyperparameter experiments, final training, Macro-F1 evaluation, a confusion matrix, error analysis, and a helper function for new predictions.

## Registration Information

| Field | Value |
|---|---|
| Assignment type | Text Analysis / NLP |
| Learning type | Classification |
| Implemented learning algorithm | Multiclass Logistic Regression using scikit-learn |
| Dataset name | Emotions dataset for NLP |
| Dataset URL | https://www.kaggle.com/datasets/praveengovi/emotions-dataset-for-nlp |

## Files

- `emotion_nlp_assignment.ipynb` - complete executed submission notebook
- `data/train.txt`, `data/val.txt`, `data/test.txt` - original Kaggle dataset splits
- `video_script_en.md` - structured five-minute presentation script
- `requirements.txt` - required Python packages
- `DATASET_SOURCE.md` - dataset source, attribution, and license information

## Running the Notebook

Open `emotion_nlp_assignment.ipynb` in Google Colab or Jupyter and select **Run all**. If the `data` directory is unavailable, the notebook attempts to download the public dataset archive directly from Kaggle.

The included notebook has already been executed and saved with all tables, plots, predictions, and evaluation results. It can therefore be reviewed on GitHub without downloading or rerunning it.

## Final Result

The executed notebook achieves approximately:

- Test Macro-F1: `0.84`
- Test Accuracy: `0.89`

Macro-F1 is the primary metric required for this multiclass classification task. Accuracy is included as a secondary measure.

## Before Submission

1. Enter the last four digits of the student ID in the notebook.
2. Confirm that the shortened student name matches the course requirements.
3. Upload the project to GitHub or the notebook to Colab with public viewing permissions.
4. Record a presentation of approximately five minutes using the included script.
5. Verify the notebook, video, and Kaggle links in a private browser window.

