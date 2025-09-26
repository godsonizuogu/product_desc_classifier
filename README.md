# Predictive Product Categorizer
Brave Fundamentals first task

In the rapidly growing field of e-commerce, accurate product categorization is essential for ensuring a seamless user experience. Properly categorized products improve search relevance, enhance product discovery, and boost customer satisfaction.

Manually assigning categories to thousands of new products is not only time-consuming but also prone to human errors. To address this, we developed a supervised machine learning model that automatically classifies products into predefined categories.

The project leverages text preprocessing, feature engineering, and supervised classification techniques. After experimenting with multiple models, the Ridge Classifier was found to deliver the best performance with strong generalization capabilities.
## Data Exploration

The dataset used for this project consists of:

Total Samples: 10,237 instances

Features: 18 features (primarily text-based product descriptions and attributes)

Target Variable: Product Category (14 distinct classes)

Categories:

Jewelry

Clothing

Mobiles & Accessories

Home Decor and Festive Needs

Computers

Tools & Hardware

Kitchen & Dining

Footwear

Baby Care

Pens & Stationery

Bags, Wallets & Belts

Toys & School Supplies

Watches

## Methodology
### 1. Data Preprocessing

Given the textual nature of the dataset, preprocessing was critical to improving classification performance. Steps included:

Text normalization

Case conversion (all text to lowercase)

Removal of unnecessary tokens: whitespace, stopwords, HTML tags, emojis, unicode characters, and punctuations

Spelling corrections

Lemmatization (to reduce words to their root forms)

Filtering: discarding non-informative words while retaining relevant parts of speech (nouns, verbs, adjectives)

Word mapping: identifying most frequently occurring words per category

Tokenization: splitting sentences into meaningful tokens

### 2. Data Splitting

Training, validation, and test sets were created to evaluate model performance.

Stratified sampling was used to preserve the class distribution across splits.

### 3. Model Training and Hyperparameter Tuning

Multiple models were tested (e.g., Logistic Regression, Naïve Bayes, Support Vector Machines).

Cross-validation (Stratified K-Fold) and GridSearchCV were applied to tune hyperparameters.

Ridge Classifier achieved the best trade-off between bias and variance.

## Results
Model Performance:

Training Accuracy: 0.997

Test Accuracy: 0.842

Additional metrics (on test set):

Precision, Recall, and F1-Score were calculated per class to account for category imbalance.

Confusion matrix analysis showed that most misclassifications occurred between clothing and footwear, as well as bags/wallets and jewelry due to overlapping descriptions.

## Conclusion and Future Work

This project demonstrates that machine learning can effectively automate product categorization in e-commerce, reducing reliance on manual effort and minimizing human errors.

Key Learnings:

Rigorous text preprocessing significantly improves model accuracy.

Cross-validation helps avoid overfitting and ensures model robustness.

Ridge Classifier offers strong baseline performance for multi-class text classification.

Future Improvements:

Advanced NLP methods: Incorporating word embeddings (Word2Vec, GloVe, FastText), or transformer-based models (BERT) for richer text representation.

Data augmentation: Expanding the dataset to handle underrepresented categories.

Ensemble methods: Combining multiple models to further boost accuracy.

Deployment: Building an API or integrating the model into a real e-commerce platform.

## Model Saving

The final Ridge Classifier model was saved using joblib, ensuring reproducibility and easy deployment.
