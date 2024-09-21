# Data
https://www.kaggle.com/datasets/prajitdatta/movielens-100k-dataset/data

# Content-based filtering
Content-based filtering (CBF) is one of the two main types of recommendation systems. CBF is an information retrieval method that uses item features to recommend items based on what users liked in the past (through implicit feedback like browsing history or explicit feedback like ratings). In contrast to collaborative filtering, which relies on user-user or item-item relationships, content-based filtering operates independently of other users' preferences, making it particularly effective in scenarios where user data is sparse or unavailable. This method leverages features of the items themselves — such as product descriptions, metadata, or textual content — to create user profiles and suggest similar items. By focusing on the attributes of the items, CBF tailors recommendations to individual preferences, ensuring that users are exposed to items aligned with their past behavior, ratings, or explicit feedback.

# Common Methods in Content-Based Filtering
Several methods are used to implement CBF to process and analyze item features to recommend similar items. Some common methods include:

### 1. TF-IDF (Term Frequency-Inverse Document Frequency)
A classical method in information retrieval, TF-IDF assigns importance to words within documents based on their frequency. In recommendation systems, TF-IDF helps to represent items as vectors in a high-dimensional space, where each dimension corresponds to a term's relevance. Similarities between items are then calculated using measures like cosine similarity. This method is simple yet effective for text-heavy datasets like movie synopses or product descriptions.
#### How It Works:
- Term Frequency (TF): Measures how often a word appears in a document.
- Inverse Document Frequency (IDF): Measures how rare or common the word is across all documents.
- The product of TF and IDF gives more weight to words that are important in specific documents but not common across all documents.
*Application:* Used to represent items (such as movies, products) as vectors in a high-dimensional space, and similarity is calculated using metrics like cosine similarity.

### 2. Naive Bayes Classifier
This probabilistic method can be used to classify items into different categories based on their features and then recommend items that belong to the same category as those the user liked.
#### How It Works:
- Naive Bayes calculates the probability that an item belongs to a particular category based on its features.
- The model recommends items that are most likely to be in the same category as items the user interacted with positively.
*Application:* Effective for categorical or discrete features in content, such as genre, author, or product category.

### 3. Decision Trees
Decision trees can be used to learn user preferences by splitting items based on their features. The model predicts whether a user would like an item based on feature values.
#### How It Works:
- The tree splits the items based on different feature values, such as genre or product type.
- The system recommends items that follow a similar decision path to those liked by the user.
*Application:* Effective for datasets where item features are more structured and categorical.

### 4. BERT (Bidirectional Encoder Representations from Transformers)
BERT is a transformer-based language model that can understand the context and semantic meaning of words in a text. In CBF, it’s used to create rich embeddings for text data that capture deeper relationships between items.
#### How It Works: 
- BERT produces dense embeddings for textual features, considering both the left and right context of words.
- The similarity between items is then calculated based on the closeness of their embeddings in the high-dimensional space.
*Application:* Particularly useful for large text datasets or when the item descriptions contain complex, nuanced language (e.g., movie plot summaries, reviews).

### 5. Convolutional Neural Networks (CNNs)
CNNs are commonly used in image recognition tasks, but they can also be applied to recommendation systems when working with visual content (e.g., recommending products based on images).
#### How It Works: 
- CNNs can extract features from item images (e.g., product photos, movie posters), which can then be used to recommend visually similar items.
*Application:* Used in CBF systems for recommending products like fashion items or movies based on their visual content.

### 6. RNNs (Recurrent Neural Networks)
RNNs are often used for sequential data and can be applied in cases where item features change over time or user interactions form sequences.
#### How It Works: 
- RNNs process sequences of user interactions with items and predict the next likely item the user may engage with.
*Application:* Effective for time-sensitive recommendations, like news articles or content streams where the sequence of interaction matters.

# Pros and Cons of Content-Based Filtering
## Pros:
- No Cold Start for Items: Since content-based systems rely on item attributes, they can recommend items to users without needing extensive interaction data. This mitigates the "cold start" problem for new items.
- Tailored to User Interests: Recommendations are personalized to users based on their explicit preferences or behavior, ensuring relevant suggestions.
- Interpretability: CBF models are often more interpretable compared to collaborative methods. It is easier to explain why a particular recommendation was made (e.g., because the user liked similar items).

## Cons:
- Limited Discovery: Content-based filtering can lead to narrow recommendations, often referred to as the "filter bubble" effect. Since the system focuses only on items similar to those the user already likes, it may fail to suggest diverse or unexpected items.
- Feature Engineering: CBF relies heavily on the quality and availability of item attributes, requiring substantial effort in feature engineering. If the features are not well-defined or representative, the model's recommendations may suffer.
- User Cold Start: While the method works well for item cold starts, it struggles with new users who haven't interacted with the system enough for it to form a meaningful profile.

# References
F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets:  
History and Context. ACM Transactions on Interactive Intelligent  
Systems (TiiS) 5, 4, Article 19 (December 2015), 19 pages.  
DOI=[http://dx.doi.org/10.1145/2827872](http://dx.doi.org/10.1145/2827872)
https://www.ibm.com/topics/content-based-filtering
https://redfield.ai/content-based-recommendation/#:~:text=These%20models%20analyze%20the%20underlying,use%20different%20models%20and%20algorithms.
Thorat, P. B., Goudar, R. M., & Barve, S. (2015). Survey on collaborative filtering, content-based filtering and hybrid recommendation system. _International Journal of Computer Applications_, _110_(4), 31-36.
BEEL, Joeran, Bela GIPP, Stefan LANGER, Corinna BREITINGER, 2016. _Research-paper recommender systems : a literature survey_. In: International Journal on Digital Libraries. 2016, **17**(4), pp. 305-338. ISSN 1432-5012. eISSN 1432-1300. doi: 10.1007/s00799-015-0156-0
Jena, Kartik & Mishra, Sushruta & Sahoo, Soumya & Mishra, Brojo. (2017). Principles, techniques and evaluation of recommendation systems. 1-6. 10.1109/ICISC.2017.8068649. 
