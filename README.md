# Subreddit Classification with Machine Learning Algorithms

### Problem Statement
---

Scraping posts from two similar subreddits, can we build a model that will be able to predict which subreddit a post came from with at least 80% accuracy? With additional tuning parameters, will we be able to push that past 80%?

### Executive Summary
---

Machine learning algorithms are some of the most powerful and interesing tools in tech right now and their applications are nearly limitless.  From predicting stock prices to determining how likely someone is to have cancer, we can use them to help us anticipate the future.  In this project, I will be using a variety of models and natural language processing techniques to try and identify what subreddit a post is from between two similar subreddits, r/Ecology and r/Environmental Science.  Additionally I will use some of the NLP packages in scikit-learn to make some inferences about some of the differences between our two subreddits.


**1. Sample details:**
- 2889 posts from r/Ecology (after processing)
- 2970 posts from r/Environmental Science (after processing)
- 4 original features
- 5 engineered features

**2. Sources:**
- https://www.reddit.com/

**3. Data Details:**


| Feature Name  | Description  | Dtype  |
|---|---|---|
| subreddit | Name of subreddit the post originated from | Object
| title  | Post title | Object |
| selftext  | Body text of the post  | Object  |
| created_utc | Coordinated universal time the post was created | int64 |
| body_char_count  | Character count of the post's body text (engineered)  | int64  |
| body_word_count  | Word count of post's body text (engineered)  | int64  |
| title_char_count  | Character count of the post's title (engineered)  | int64  |
| title_word_Count  |  Word count of post's title (engineered) | int64  |  
| target | binarized bool target variable to identify which subreddit the post originated from (engineered) | int64 | 



**4. Target:**

Three classifiction models were used: Multinomial Naïve Bayes, Random Forest Classifier, and SVC to predict post origin using body text and title.


**5. Model Performance:**

A total of five models were fit using many different parameters.

| Model Type  | NLP  | Score  |
|---|---|---|
| Naïve Bayes   | Count vectorizer  | 77.5  |
| Naïve Bayes  | TF-IDF  | 79.7  |
| Random Forest  | Count vectorizer  | 80.4  |
| Random Forest | TF-IDF  | 80.1 |
| SVM | Count vectorizer | 78.9 |



### Conclusion
---

All scores surpassed our null hypothesis fo 50.7 with a satisfactory overall accuracy of 80.4 and recall of 82.5.

With additional posts I think we could possibly squeeze a bit more performance out of our models, however, if we call the EDA there were a lot of similarities in our posts so 80.4% accuracy is great.  Perhaps a KNN or logisitic regression would perform better but with the time allotted and how resource/time intensive running some of these gridsearches is, we're going to stick with this single model for now.

### Inferences

From our intial EDA we observed that both subreddits have a large number of posts pertaining to questions about jobs/work as well as questions about higher education in the fields of ecology and environmental science.  From our NLP, it appears that that the environmental science subreddit tends to be slightly more focused on work and educational endeavors where as the ecology subreddit has more posts about research, field experience, and plant and animal species.
Some additional metrics:
# project_3
