# Music Recommendation System: Model Comparison and Insights

This project explores how music recommendation systems can be optimized for user engagement using collaborative filtering, matrix factorization, and clustering-based approaches. We evaluate multiple models using real-world user-song interaction data and compare their performance through key metrics.

This project was developed as the final capstone for the [Berkeley ExecEd Professional Certificate in Machine Learning and Artificial Intelligence](https://em-executive.berkeley.edu/professional-certificate-machine-learning-artificial-intelligence).

## Project Objective

To investigate the effectiveness of various recommendation strategies in predicting user preferences, and determine which models best balance precision, recall, and overall F1 score.

## Data Sources

- Files Used:
  - `song_data.csv`: Contains metadata about tracks, such as their IDs, titles, artist_names, releases (album name), and years the songs were published.
  - `count_data.csv`: Contains user interaction data such as user IDs, song IDs, and the count of times the song was played by those users.
- Records:
  - `song_data.csv`: ~1,000,000 songs
  - `count_data.csv`: ~2,000,000 listening events
- Key Features:
  - `song_data.csv`: `song_id`, `title`, `artist_name`, `release`, `year`
  - `count_data.csv`: `user_id`, `song_id`, `play_count`

Note: Due to the size of the dataset, it is not included in this repository. You can download the required data from the official Million Song Dataset: [http://millionsongdataset.com/](http://millionsongdataset.com/).

## Methodology
- **Preprocessing**:
  - Encoded user and song IDs
  - Filtered long-tail user and item distributions
  - Normalized play count values
- **Models Trained**:
  - **User-User Collaborative Filtering**: Recommends songs to a user based on the preferences of other users with similar behavior. It relies on finding "neighbors" with shared listening patterns.
  - **Item-Item Collaborative Filtering**: Suggests songs similar to those a user has already enjoyed. This method focuses on the similarity between items based on user interactions.
  - **SVD (Singular Value Decomposition)**: A matrix factorization technique that captures latent features of users and items, allowing more nuanced recommendations even with sparse data.
  - **Co-Clustering**: Groups both users and items simultaneously into clusters, and makes predictions based on interactions between these groups. It can uncover hidden structure in the data not captured by other methods.
- **Evaluation Techniques**:
  - **Root Mean Square Error (RMSE)**: Measures the average magnitude of prediction errors. Lower RMSE indicates better accuracy in estimating user preferences.
  - **Precision@K**: Indicates the proportion of recommended songs in the top-K list that are relevant. Higher precision means fewer irrelevant recommendations.
  - **Recall@K**: Reflects the proportion of relevant songs successfully recommended within the top-K list. Higher recall implies better coverage of user interests.
  - **F1 Score**: The harmonic mean of precision and recall. A higher F1 Score signals a strong balance between relevance and coverage.
- **Tuning**:
  - **GridSearchCV** and custom thresholds to optimize top-K performance
    
## Findings

At a threshold of 1.15, tuned models demonstrated the following performance:

### Precision Comparison

![Precision Plot](precision_plot.png)

### Recall Comparison

![Recall Plot](recall_plot.png)

### F1 Score Comparison

![F1 Score Plot](f1_score_plot.png)

Observations:

- SVD Tuned and User-User Tuned models consistently balanced high recall with respectable precision, leading to the best F1 scores.
- Co-Clustering offered decent recall but lagged slightly in precision.
- Hyperparameter tuning generally improved model performance across all metrics.

## Conclusion

This project demonstrates the strengths and trade-offs of different recommendation techniques. It shows that tuning hyperparameters significantly boosts performance, especially when optimizing for F1 Score.

The work serves as a foundation for building more nuanced, scalable, and personalized recommendation engines.

## Technologies Used

- Python, Pandas, NumPy
- Surprise Library
- Matplotlib and Seaborn for Visualization
- NLTK for basic text processing

## Author

This project was developed as part of a professional development journey in data science, with the goal of understanding recommendation systems from both a technical and strategic perspective.
