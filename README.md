# Music Recommendation System - Final Project

This repository contains the code and documentation for a **Music Recommendation System** developed as part of a machine learning and deep learning course. The system is designed to recommend the top 10 songs to users based on their listening history and preferences using various recommendation techniques such as content-based filtering, collaborative filtering, and deep learning models.

## Project Overview

Music recommendation systems are essential for users to discover new songs they might like. This project utilizes data science and machine learning techniques to create personalized recommendations, enhancing the music discovery experience for users.

### Objective

The primary goal is to develop a recommendation system that suggests songs a user is likely to enjoy, leveraging both content-based and collaborative filtering techniques. We tested and evaluated several models to determine the most effective approach for providing personalized song recommendations.

## Dataset

The project uses the **Taste Profile Subset** from the **Million Song Dataset**. The dataset consists of two main files:

- **Song Data**: Contains metadata about the songs, including `song_id`, `title`, `artist`, `release year`, etc.
- **User Interaction Data**: Contains `user_id`, `song_id`, and `listen_count` (how many times a user played a particular song).

These files were downloaded from external sources, and preprocessing steps were applied to clean and merge the data for use in the recommendation system.

## Models and Approaches

### 1. **Content-Based Filtering**
- **TF-IDF (Term Frequency-Inverse Document Frequency)** was used to vectorize song features such as song title and artist.
- **Cosine Similarity** was then used to calculate the similarity between songs, allowing us to recommend songs that are similar to those a user has already listened to.

### 2. **Collaborative Filtering**
- **Matrix Factorization (SVD)**: A collaborative filtering method that learns latent factors from the interaction matrix (user-song play counts).
- **KNN-Based Collaborative Filtering**: Utilizes the K-Nearest Neighbors algorithm to recommend songs by finding users with similar listening histories.
- **Clustering-Based Collaborative Filtering**: Uses **CoClustering** to group users and songs into clusters, and recommendations are made based on cluster similarities.

### 3. **Deep Learning (Neural Networks)**
- A **Keras-based neural network** was implemented, where user and song embeddings were learned in a latent space. The network predicts a user’s preference for a song based on learned features.


## Evaluation

The models were evaluated using the following advanced metrics, incorporating a threshold-based approach to refine recommendation relevance:

### **Threshold-Based Evaluation Approach**
In this project, we applied a **threshold-based system** to define relevance. A song is considered **relevant** if its actual rating meets or exceeds a certain threshold (e.g., a rating of 3 or more). Similarly, a song is considered **recommended** if its predicted rating meets or exceeds a specific threshold (e.g., a prediction score of 3 or more). 

This thresholding mechanism ensures that only songs with sufficiently high predicted and actual ratings are considered when calculating evaluation metrics.

### **Precision@K**
**Precision@K** measures how many of the top K recommended songs are relevant (i.e., meet the relevance threshold for both prediction and rating). It indicates the accuracy of the recommendations at K.

Formula:
```
Precision@K = (Number of relevant items in top K recommendations) / (Number of items recommended at K)
```

For example, if 7 out of the top 10 recommended songs meet the relevance threshold, the **Precision@10** would be:
```
Precision@10 = 7 / 10 = 0.7
```

### **Recall@K**
**Recall@K** measures how many of the relevant songs (based on actual ratings) were successfully recommended in the top K recommendations. This metric focuses on the system's ability to retrieve all relevant items.

Formula:
```
Recall@K = (Number of relevant items in top K recommendations) / (Total number of relevant items)
```

For example, if a user has 8 songs in total that meet the relevance threshold and 6 of them are successfully recommended in the top 10 predictions, the **Recall@10** would be:
```
Recall@10 = 6 / 8 = 0.75
```

### **F1-Score@K**
The **F1-Score@K** balances Precision and Recall. It is useful when combining both metrics to achieve a good balance between recommending enough relevant items and keeping accuracy high.

Formula:
```
F1-Score@K = 2 * (Precision@K * Recall@K) / (Precision@K + Recall@K)
```

### **Mean Squared Error (MSE)**
MSE measures the average squared difference between actual and predicted values for play counts. A lower MSE indicates better performance by the model in predicting user interactions with songs.

### **Mean Absolute Error (MAE)**
MAE measures the average absolute difference between predicted and actual values. It helps evaluate how close the predicted play counts are to the actual values, offering a more interpretable error metric alongside MSE.

### **Model Comparison**
- **Precision@K** and **Recall@K** were the key metrics used to compare how well the models recommended relevant songs to users, considering the threshold-based relevance.
- **Matrix Factorization (SVD)** performed the best in delivering personalized recommendations.
- **Content-based filtering** (TF-IDF + Cosine Similarity) was effective at finding similar songs but less effective in personalizing recommendations compared to collaborative filtering models.

---

This version uses plain text for equations, making it compatible with GitHub Markdown. Let me know if you'd like further refinements!

## Results

- **Matrix Factorization (SVD)** emerged as the best-performing model for personalized song recommendations.
- **Content-based filtering** was effective in recommending similar songs but did not personalize recommendations as well as collaborative filtering techniques.
- A **hybrid approach** combining content-based and collaborative filtering models is recommended for achieving the most accurate and personalized recommendations.

## Installation and Setup

To run the project locally just click on the 'Open in Colab' at the top of the file.

## Usage

1. **Preprocessing**: The notebook walks through data preprocessing, including downloading the dataset, cleaning it, and merging user interactions with song metadata.
2. **Model Building**: Several models are built for generating song recommendations, including content-based filtering, collaborative filtering, and deep learning methods.
3. **Evaluation**: The models are evaluated, and predictions are generated for top 10 song recommendations for each user.

## Future Work

- Implement additional hybrid models that combine content-based and collaborative filtering techniques for improved recommendation accuracy.
- Explore other deep learning architectures, such as recurrent neural networks (RNNs), for capturing sequential patterns in user behavior.
- Experiment with more advanced techniques like **autoencoders** and **reinforcement learning** to improve user experience in the recommendation system.

## Contributors

- **Ariel Hedvat**
- **Shiraz Israeli**
- **Yuval Bakirov**
- **Eitan Bakirov**
- 


