# Movies-Recommendation-System

A collaborative filtering-based movie recommendation system built to deliver personalized movie suggestions for streaming platforms.

##  Team

**Authors:** Winnie Njoroge, Michelle Mwende, Laban Leploote, Alice Mathenge, Dean Mutie

##  Overview

This project addresses the critical challenge of subscriber retention in the competitive streaming landscape, where customer acquisition costs are 5x higher than retention. By implementing advanced recommendation algorithms, we combat cognitive overload and enhance user engagement through personalized content discovery.

##  Business Objective

Develop a recommendation system that:
- Reduces subscriber churn by improving content discoverability
- Increases user engagement through personalized recommendations
- Achieves RMSE < 1.0 for rating predictions
- Handles both existing and new user scenarios

##  Dataset

**MovieLens 100K Dataset** from GroupLens Research
- **100,836 ratings** from 610 users across 9,742 movies
- Rating scale: 0.5 to 5.0 stars
- ~165 ratings per user on average
- Data includes user ratings, movie metadata, and genre information

##  Methodology

### Models Evaluated
1. **Baseline Model** - Global average (benchmark)
2. **SVD** - Singular Value Decomposition (matrix factorization)
3. **KNN-Based** - User and item similarity approaches
4. **NMF** - Non-negative Matrix Factorization
5. **BaselineOnly** - User and item bias modeling

### Key Features
- Train-validation-test split strategy for robust evaluation
- Hyperparameter tuning via GridSearchCV
- Ensemble methods for improved performance
- Comprehensive data sparsity analysis (94.14% sparse matrix)

##  Results Before Tuning

<img width="1586" height="590" alt="image" src="https://github.com/user-attachments/assets/d0346fd4-8773-479c-ba29-6eef645d9e2f" />


| Model | RMSE | MAE | Performance |
|-------|------|-----|-------------|
| **SVD (Production)** | **0.8566** | **0.6575** | **Best Overall** |
| BaselineOnly | 0.8536 | 0.6561 | Best Validation |
| KNNWithMeans | 0.8601 | 0.6597 | Competitive |
| NMF | 0.8872  | 0.6807 | Interpretable |
| KNNBasic | 0.9414   | 0.7300 | Interpretable |

## Results After Tuning

<img width="1586" height="590" alt="image" src="https://github.com/user-attachments/assets/80745306-b430-418a-9510-f1f3b25e0b45" />


**Selected Model:** SVD with optimized hyperparameters
- Exceeds RMSE target (0.8703 < 1.0)
- Captures complex latent patterns in user preferences
- Balances accuracy with computational efficiency

##  Key Insights

1. **Rating Patterns**: Users exhibit positive rating bias (mean: 3.5 stars)
2. **Genre Distribution**: Drama dominates (4,361 movies), 11.4x more common than War
3. **User Engagement**: Highly variable (20-2,698 ratings per user)
4. **Data Sparsity**: 94.14% sparse matrix typical for collaborative filtering

## 📽 TOP 5 MOVIE RECOMMENDATIONS FOR USER 1

| Rank | Movie Title | Predicted Rating | Average Rating | Genres |
|------|-------------|------------------|----------------|--------|
| 1 | Shawshank Redemption, The (1994) | 5.00 | 4.43 (317 ratings) | Crime, Drama |
| 2 | Dark Knight, The (2008) | 5.00 | 4.24 (149 ratings) | Action, Crime, Drama, IMAX |
| 3 | Philadelphia Story, The (1940) | 5.00 | 4.31 (29 ratings) | Comedy, Drama, Romance |
| 4 | Rear Window (1954) | 5.00 | 4.26 (84 ratings) | Mystery, Thriller |
| 5 | North by Northwest (1959) | 5.00 | 4.18 (57 ratings) | Action, Adventure, Mystery, Romance, Thriller |

##  Deployment Recommendations

### Primary Strategy
- Deploy **SVD model** for production use
- Implement A/B testing framework to validate recommendations
- Monitor key metrics: click-through rate, watch time, user satisfaction

### Cold Start Solutions
- Popularity-based recommendations for new users
- Content-based filtering for new movies
- Hybrid approach combining collaborative and content-based methods

##  Next Steps

**Immediate (2 Weeks)**
- Stakeholder presentation with live demo
- Production deployment of SVD model
- Implement monitoring infrastructure

**Short-term (1-3 Months)**
- A/B testing against current system
- Develop hybrid recommendation approach
- Build real-time recommendation API

**Long-term (3-6 Months)**
- Scale to deep learning models (Neural Collaborative Filtering)
- Incorporate implicit feedback signals
- Multi-modal recommendations (context-aware)

## 🛠️ Technologies Used

- **Python** - Core programming language
- **Pandas & NumPy** - Data manipulation
- **Scikit-surprise** - Collaborative filtering algorithms
- **Matplotlib & Seaborn** - Data visualization
- **Scikit-learn** - Model evaluation and optimization

##  Repository Structure

```
MovieLens-Recommendation-System/
│
├── Data/
│   ├── ratings.csv              # User-movie ratings
│   ├── movies.csv               # Movie metadata
│   ├── tags.csv                 # User-generated tags
│   └── links.csv                # External movie IDs
│
├── Movie_recommendation_system_FINAL.ipynb
│   └── Complete analysis pipeline
│       ├── 1. Business Understanding
│       ├── 2. Data Understanding
│       ├── 3. Data Preparation
│       ├── 4. Exploratory Data Analysis
│       ├── 5. Modeling
│       │   ├── Baseline
│       │   ├── SVD
│       │   ├── KNN Methods
│       │   ├── NMF
│       │   ├── BaselineOnly
│       │   └── Hyperparameter Tuning
│       └── 6. Conclusions & Recommendations
│
├── README.md                    # This file
│
└── requirements.txt             # Python dependencies

```
## 🎓 Conclusion

This project successfully demonstrates that collaborative filtering can deliver accurate, personalized movie recommendations with RMSE of 0.8703, exceeding the business target. The SVD model balances prediction accuracy with computational efficiency, making it ideal for production deployment in streaming platforms.


**Contact:** For questions or collaboration opportunities, please reach out to the project team.
