# Link Prediction in Social Networks

## Data Overview
The data for this project was taken from Facebook's recruiting challenge on Kaggle, available at [Facebook Recruiting Challenge](https://www.kaggle.com/c/FacebookRecruiting). The dataset contains two columns: `source_node` and `destination_node`, representing each edge in the graph.

## Overview
This project aims to predict links in a social network graph using supervised learning. The process involves data preparation, exploratory data analysis (EDA), feature generation, model training, and evaluation.

## Data Preparation and EDA
- Calculate the number of followers for each person.
- Calculate the number of people each person is following.
- Calculate the sum of followers and following for each person.
- Generate additional edges for supervised learning, ensuring they are not already present in the graph.

## Feature Generation
For each edge in the graph and the generated edges:
- Calculate similarity measures (Jaccard Distance, Cosine Distance, PageRank, Adamic/Adar Index, etc.).
- Determine if the person was following back.
- Calculate Katz Centrality and HITS score.
- Generate weight features (weight of incoming edges, weight of outgoing edges, etc.).

## Labeling "Bad" Links
Identify edges that are not in the graph and have a shortest path greater than 2. These will serve as negative examples in training.

## Training and Test Data Split
- Remove edges from the graph and use them as test data.
- Use the modified graph (with removed edges) to create features for both train and test data.

## Model Training and Evaluation
- Train a supervised learning model (e.g., logistic regression, random forest) using the generated features and the labeled data.
- Evaluate the model using metrics such as accuracy, precision, recall, and F1-score.

## Future Work
- Incorporate additional features or algorithms for improved link prediction.
- Experiment with different data splitting strategies or model architectures.
