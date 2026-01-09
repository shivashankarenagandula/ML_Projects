This project is a classification system built using the MNIST handwritten digit dataset.
The goal of the project is to train a machine learning model to decide whether a given handwritten digit image represents the digit “5” or not.

Instead of directly solving the harder problem of classifying all digits (0–9), this project focuses on a binary classification task (5 vs not-5) to clearly understand how classification models make decisions and how their performance should be evaluated.

How the Data Is Represented

Each MNIST image is 28 × 28 pixels, which results in 784 numerical values per image.
Each value represents the intensity of a pixel, where:

0 means white

255 means black

The model does not see images like humans; it only sees these 784 numeric features for each image.

Classification Approach

This project uses supervised learning, where:

Input: pixel values of handwritten digit images

Output: a class label indicating whether the image is a digit 5 or not

A machine learning classifier is trained on labeled data so it can learn patterns that distinguish the digit 5 from other digits.

Model Used

The project uses SGDClassifier, a fast and scalable linear classifier trained using stochastic gradient descent.
Instead of directly predicting class labels, the model produces a confidence score for each image, representing how strongly the image looks like the digit 5.

Decision Scores and Threshold

The model outputs a decision score, not a final yes/no answer.
A threshold is applied to this score:

If the score is greater than or equal to the threshold → predict digit 5

Otherwise → predict not digit 5

By default, models use a fixed threshold, but this project goes a step further by tuning the threshold based on evaluation needs.

Evaluation Metrics

Accuracy alone is not sufficient for classification problems, especially when classes are imbalanced.
This project evaluates performance using:

Confusion Matrix – to understand types of mistakes

Precision – how often predicted 5s are actually correct

Recall – how many real 5s are correctly detected

ROC-AUC – to measure overall ranking performance

These metrics provide a deeper understanding of model behavior.

Extra Feature 1: Automatic Threshold Tuning

A custom threshold-tuning method was added to automatically select a decision threshold that meets a target precision level (for example, 95%).

This feature demonstrates how classification systems can be adjusted to meet business or real-world requirements, such as minimizing false positives in sensitive applications.

Extra Feature 2: Error Analysis Visualization

Instead of relying only on numbers, this project includes visual error analysis:

False Positives: images predicted as 5 but actually not 5

False Negatives: real 5s that the model failed to detect

The project displays these images to understand why the model makes mistakes, which is a critical step in building reliable machine learning systems.
