# European Union Parliamentary Debate Clustering

## Overview
This project performs topic clustering on European Union parliamentary debates from 2022 using natural language processing and machine learning techniques. The goal is to identify distinct thematic clusters within parliamentary discussions to understand the main topics of debate.

## Methodology

### Data Preprocessing
- **Text Filtering**: Debates with fewer than 300 characters are filtered out to ensure meaningful content
- **TF-IDF Vectorization**: Converts debate text into numerical features using Term Frequency-Inverse Document Frequency
  - Custom stopwords added for EU-specific terms (e.g., 'europe', 'commission', 'parliament')
  - Token pattern: words with 3+ characters
  - Maximum document frequency: 70%
  - Minimum document frequency: 25 documents
  - Maximum features: 10,000

### Dimensionality Reduction
- **Truncated SVD**: Reduces the high-dimensional TF-IDF matrix from 10,000 features to 500 components

### Clustering
- **Algorithm**: K-Means clustering
- **Optimal Clusters**: 4 clusters were selected based on:
  - Distinctiveness of top terms within each cluster
  - Clear separation in 2D PCA visualization
  - Silhouette score analysis

## Results

### Cluster Topics Identified

**Cluster 1: Gender & Women's Rights**
- Top terms: women, violence, gender, rights, abortion, girls, equality, sexual, men, right
- Focus: Gender equality, women's rights, and related social issues

**Cluster 2: Ukraine & Russia Conflict**
- Top terms: ukraine, people, war, rights, russia, law, putin, democracy, country, russian
- Focus: Russian invasion of Ukraine, international relations, democracy

**Cluster 3: Social & Environmental Policy**
- Top terms: climate, member, states, work, people, social, health, food, citizens, digital
- Focus: Climate change, social policies, health, food security, digital transformation

**Cluster 4: Energy & Economic Crisis**
- Top terms: energy, gas, prices, renewable, price, crisis, electricity, nuclear, market, fossil
- Focus: Energy policy, price crisis, renewable energy, nuclear power

### Visualization
- **2D PCA Plot**: Shows clear separation between the four clusters
- **PCA Components Analysis**: Reveals the main contributing terms for each principal component

## Files

- `kddmhw2.ipynb`: Main Jupyter notebook containing the clustering analysis
- `debates_2022.csv`: Dataset of EU parliamentary debates
- `requirements.txt`: Python package dependencies
- `README.md`: This documentation file
