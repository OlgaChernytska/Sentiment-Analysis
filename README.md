## Sentiment Analysis

Purpose: build a model that classifies reviews as positive/negative. Data for training and testing - film reviews with ranking from Rotten Tomatoes and IMDb. Train set contains 106436 observations, test set - 45783. Share of positive reviews - 58.7%. 


The model was developed in three stages:
1) Preprocessing. Using regular expressions, reductions were replaced, actor and film names were removed as well as dates. Then text was converted to lowercase. Text was tokenized using function word_tokenize from nltk.tokenize library. Tokens were stemmed using SnowballStemmer from nltk.stem library. Stopwords were removed.
2) Vectorization. Reviews were vectorized using Count Vectorizer with unigrams and bigrams. Additional features were extracted, such as number of symbols, tokens and sentences, number of question marks and exclamation marks, polarity of the first and last sentences in the review.
3) Model Training. Model was trained using xgboost library. Parametes num_round, eta, max_depth and min_child_weight were additionaly tuned.

Result: Test set accuracy - 80.2%.


## Web Scraping from Amazon

This folder contains dataset with book reviews from Amazon.com and script for collecting this dataset.

R script. For web scraping was used 'rvest' library. Script consists of two parts. Part 1 scraps Amazon to make a list of books and links to their reviews and saves it to database 'book_list', where field 'id' - unique Amazon product code. Part 2 scraps reviews of the books from the book list and saves them to file.

Dataset. Contains ~63,000 book reviews from www.amazon.com. Ranking varies from 1 to 5 stars.
Average ranking - 4.543, median ranking - 5. Set hightly unbalanced.
Average review length - 40.6 words and 221.1 symbols.
10 the most frequent words: the, and, to, I, a, of, is, in, book, this.
Number of reviews that have 1-2 words - 9%; 3-9 words - 20%; 10-49 words - 50%; 50+ words - 21%.
Number of Duplicates: 5427

