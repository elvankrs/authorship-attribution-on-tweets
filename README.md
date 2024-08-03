# Authorship Attribution on Tweets - README

## Project Overview
This project aims to determine the author of a given tweet using machine learning techniques, focusing on both closed set and open set approaches. Closed set attribution involves known authors during training and testing, while open set attribution includes unknown authors at test time.

## Dataset
The Sentiment140 dataset is used for this project. It contains 1.6 million tweets. For this task, we select the top 50 users with the most tweets, ensuring each user has more than 150 tweets. The dataset is divided into training, validation, and test sets with 75, 35, and 20 tweets per user, respectively. An additional 3157 tweets from unknown authors are added for the open set approach.

## Preprocessing
Preprocessing steps include:
- Replacing times, dates, mentions, and URLs with placeholder tokens.
- Removing users whose tweets are identical, to avoid misleading performance evaluations.

## Feature Extraction
We use Term Frequency-Inverse Document Frequency (TF-IDF) for feature extraction. Both character-level 4-grams and word-level n-grams are utilized to capture different aspects of the tweets.

## Model
For the open set approach, we modified the k-Nearest Neighbors (kNN) algorithm to include a reject option based on distance thresholds. This allows the model to reject samples from unknown authors. Various threshold percentiles and number of neighbors (k) are experimented with to optimize performance.

## Experiments
The experiments involve testing different feature extraction methods, dimensionality of the feature space, threshold percentiles, and number of neighbors. The performance is measured using F1 scores for closed set classification and rejection accuracy for the open set approach.

## Conclusion
The best performance was achieved using a combination of character-level 4-grams and word-level 1-grams features. The kNN model with a rejection option provided a balance between classification and rejection accuracy. The project demonstrates the challenges of authorship attribution, especially with social media data.


3. Go, A., Bhayani, R., & Huang, L. (2009). Twitter sentiment classification using distant supervision. Retrieved from [Sentiment140](http://help.sentiment140.com/home)

