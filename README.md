# Music Recommendation System: Model Comparison and Insights

This project explores how music recommendation systems can be optimized for user engagement using collaborative filtering, matrix factorization, and clustering-based approaches. We evaluate multiple models using real-world user-song interaction data and compare their performance through key metrics.

## Project Objective

To investigate the effectiveness of various recommendation strategies in predicting user preferences, and determine which models best balance **precision**, **recall**, and **overall F1 score**.

## Data Sources

- **Interaction Data**: User-song listening history with play counts.
- **Metadata**: Song information including title, artist, album, and release year.

## Models Evaluated

The project includes both untuned and optimized versions of the following models:

- User-User Collaborative Filtering
- Item-Item Collaborative Filtering
- Singular Value Decomposition (SVD)
- Co-Clustering

We use the `Surprise` library for model implementation and tuning.

## Evaluation Metrics

We assess models at different rating thresholds using:
- **Root Mean Square Error (RMSE)**
- **Precision@K**
- **Recall@K**
- **F1 Score**

## Findings

At a threshold of **1.15**, tuned models showed the following performance:

### Precision Comparison

![Precision Plot](path/to/your/precision_plot.png)

### Recall Comparison

![Recall Plot](path/to/your/recall_plot.png)

### F1 Score Comparison

![F1 Score Plot](path/to/your/f1_score_plot.png)

- **SVD Tuned** and **User-User Tuned** models consistently balanced high recall with respectable precision, leading to the best F1 scores.
- **Co-Clustering** offered decent recall but lagged slightly in precision.
- Tuning generally improved model performance across all metrics.

## Conclusion

This project demonstrates the strengths and trade-offs of different recommendation techniques. It shows that **tuning hyperparameters significantly boosts performance**, especially when optimizing for F1 Score.

This work lays a foundation for building more nuanced, scalable, and personalized recommendation engines.

---

## Technologies Used

- Python, Pandas, NumPy
- Surprise Library
- Matplotlib & Seaborn for Visualization
- NLTK for basic text processing

---

## Author

This project was built as part of my learning journey in data science with the goal of understanding recommendation systems from both a technical and strategic perspective.
