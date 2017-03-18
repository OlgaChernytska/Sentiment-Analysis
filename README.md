## Sentiment Analysis

Purpose: build a model that classifies reviews as positive/negative. Data for training and testing - film reviews with ranking from Rotten Tomatoes and IMDb. Train set contains 106436 observations, test set - 45783. Share of positive reviews - 58.7%. 


The model was developed in three stages:
1) Preprocessing. Using regular expressions, reductions were replaced, actor and film names were removed as well as dates. Then text was converted to lowercase. Text was tokenized using function word_tokenize from nltk.tokenize library. Tokens were stemmed using SnowballStemmer from nltk.stem library. Stopwords were removed.
2) Vectorization. Reviews were vectorized using Count Vectorizer with unigrams and bigrams. Additional features were extracted, such as number of symbols, tokens and sentences, number of question marks and exclamation marks, polarity of the first and last sentences in the review.
3) Model Training. Model was trained using xgboost library. Parametes num_round, eta, max_depth and min_child_weight were additionaly tuned.

Result. Test set accuracy - 80.2%.
