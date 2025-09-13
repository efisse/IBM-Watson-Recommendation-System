# IBM Watson Studio Recommendation System

##  Project Overview

This project implements a comprehensive recommendation system for the IBM Watson Studio platform, designed to enhance user experience by connecting users with relevant articles, datasets, notebooks, and other AI/ML assets. The system employs multiple recommendation approaches to provide personalized content suggestions.

##  Features

- **Multiple Recommendation Algorithms**: Implements 4 different recommendation approaches
- **Scalable Architecture**: Handles large datasets efficiently with sparse matrices
- **Comprehensive Analysis**: Detailed exploratory data analysis and performance evaluation
- **Production Ready**: Well-documented, tested, and optimized code
- **Interactive Notebook**: Complete implementation in Jupyter notebook format

##  Recommendation Approaches

### 1. Rank-Based Recommendations
- **Purpose**: Popularity-based recommendations for new users
- **Algorithm**: Article ranking by interaction count
- **Best For**: Cold start problem, trending content discovery
- **Performance**: 14.24% coverage with top 10 articles

### 2. User-User Collaborative Filtering
- **Purpose**: Personalized recommendations based on similar users
- **Algorithm**: Cosine similarity between user interaction patterns
- **Best For**: Existing users with interaction history
- **Features**: Improved ranking with user activity weighting

### 3. Content-Based Recommendations
- **Purpose**: Recommendations based on article content similarity
- **Algorithm**: TF-IDF vectorization + KMeans clustering
- **Best For**: Content discovery, new articles without interaction history
- **Clusters**: 14 optimal content clusters identified

### 4. Matrix Factorization (SVD)
- **Purpose**: Latent factor-based recommendations
- **Algorithm**: Singular Value Decomposition
- **Best For**: High-quality personalized recommendations
- **Performance**: 95% variance explained with 249 components

##  Project Structure

```
recommendation_system/
├── data/
│   ├── user-item-interactions.csv    # User interaction data
│   └── articles_community.csv        # Article content and metadata
├── recommendation_system_notebook.ipynb    # Project Notebook                 
├── README.md                         # Project documentation
└── requirements.txt                  # Python dependencies
```

##  Installation & Setup

### Prerequisites
- Python 3.8+
- pip package manager

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/efisse/IBM-Watson-Recommendation-System.git
   cd IBM-Watson-Recommendation-System
   ```

2. **Create virtual environment**
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the notebook**
   ```bash
   jupyter notebook recommendation_system_notebook.ipynb
   ```

##  Dataset Information

### User-Item Interactions Dataset
- **Size**: 45,993 interactions
- **Users**: 5,148 unique users
- **Articles**: 714 unique articles with interactions
- **Sparsity**: 99.08%
- **Features**: User email, article ID, article title

### Articles Dataset
- **Size**: 1,056 articles
- **Features**: Article content (doc_body, doc_description), metadata
- **Content**: IBM Watson Studio articles, tutorials, and resources

### Key Statistics
- **Median interactions per user**: 3
- **Most active user**: 364 interactions
- **Most popular article**: 937 interactions
- **Average interactions per article**: 64.42

##  Usage

### Running the Complete Notebook

1. **Execute all cells** in `recommendation_system_notebook.ipynb`
2. **Follow the cell-by-cell implementation** for step-by-step analysis
3. **Review the results** and recommendations generated


##  Performance Metrics

### Coverage Analysis
- **Top 5 articles**: 8.27% of all interactions
- **Top 10 articles**: 14.24% of all interactions
- **Top 20 articles**: 24.05% of all interactions
- **Top 50 articles**: 42.35% of all interactions

### Model Performance
- **Gini Coefficient**: 0.6657 (indicates high popularity inequality)
- **SVD Explained Variance**: 95% with 249 components
- **Content Clusters**: 14 optimal clusters for content similarity
- **Matrix Sparsity**: 99.08% (typical for recommendation systems)

##  Technical Implementation

### Key Libraries
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computations
- **scikit-learn**: Machine learning algorithms
- **scipy**: Sparse matrix operations
- **matplotlib/seaborn**: Data visualization

### Algorithm Details
- **TF-IDF Vectorization**: 5,000 features with unigrams and bigrams
- **KMeans Clustering**: Optimal cluster selection using elbow method
- **Cosine Similarity**: User and article similarity calculations
- **SVD Decomposition**: TruncatedSVD for matrix factorization

##  Project Requirements Met

###  Code Functionality and Readability
- [x] All code is functional and passes tests
- [x] Well-documented functions with docstrings
- [x] DRY principles implemented
- [x] Modular design with clear separation of concerns

###  Part I & II: Data Exploration & Rank Based Recommendations
- [x] Complete exploratory data analysis
- [x] All rubric variables calculated correctly
- [x] Rank-based recommendation functions implemented
- [x] Top article IDs and names functions working

###  Part III: Collaborative Filtering
- [x] User-item matrix created (5,148 × 714)
- [x] Similar user finding implemented
- [x] User-user collaborative filtering working
- [x] Improved recommendations with ranking
- [x] New user handling implemented

###  Part IV: Content Based Recommendations
- [x] TF-IDF vectorization with optimal parameters
- [x] KMeans clustering with optimal clusters
- [x] Content similarity recommendations working
- [x] Article clustering analysis completed

###  Part V: Matrix Factorization
- [x] SVD performed on user-item matrix
- [x] U, Sigma, Vt matrices generated
- [x] Optimal latent features selected (249 for 95% variance)
- [x] Article-article recommendations using cosine similarity
- [x] Reconstruction quality analysis completed

##  Future Improvements

1. **Hybrid Approaches**: Combine multiple methods for better performance
2. **Deep Learning**: Implement neural networks for complex pattern recognition
3. **Real-time Updates**: Stream recommendations for dynamic content
4. **Context Awareness**: Include temporal and contextual factors
5. **Explainability**: Provide explanations for recommendations
6. **A/B Testing**: Implement evaluation framework with real users

##  Evaluation Methods

To test recommendation quality in practice:

1. **A/B Testing**: Compare different approaches with real users
2. **Cross-Validation**: Use historical data to predict future interactions
3. **Diversity Metrics**: Measure recommendation diversity and novelty
4. **Coverage Analysis**: Ensure recommendations cover the full article catalog
5. **User Satisfaction Surveys**: Collect explicit feedback on recommendations


