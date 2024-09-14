# What characteristics make K-beauty unique compared to American skincare brands?
#### Problem statement:

An American skincare company is transitioning to an American-Korean-based company and aiming to incorporate Korean skincare into their line. They are seeking to classify their skincare products as American or Korean and differentiate the new products for marketing. The project aims to build a classification model and provide insights to support marketing decisions in line with the company's mission and also be added to their system.

---

### Datasets ###
The data was obtained by scraping the Skincare Addiction and Korean Skincare subreddits on Reddit. Skincare Addiction focuses on general skin care concerns, while the Korean skincare subreddit emphasizes Korean-based products and ingredients.

---

### Data Dictionary ###

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**created_utc**|*object*|Reddit|Data converted to UTC| 
|**title**|*object*|Reddit|Post titles from reddit|
|**self_text**|*object*|Reddit|Posts|
|**subreddit **|*object*|Redit|Which subreddit, Korean skincare or skincare addiction|
---
### Exploratory Data Analysis ###

As I identified the data, I took appropriate measures by using count vectorization, testing whether to use lemmanization or tokenization. I also removed some Korean text for this analysis. ![word cloud](https://github.com/aychziel/K-Beauty-vs-American-Skincare/blob/main/plots/word_cloud_eda.png) 

Some of my findings for both skincare subreddits were that.. 

![bigrams](https://github.com/aychziel/K-Beauty-vs-American-Skincare/blob/main/plots/common_bigrams_both_skincare_reddits.png) 

The Top written about Brands included 
- Beauty of Joseon, La Roche Posay, and cosrx.

The Top written about Ingredients include 
- Snail Mucin, Cleansing oil, Hyaluronic Acid and Salicylic Acid.

Lastly, the Top written about skin concerns include 
- Acne Prone, Dry Skin, Sensitive skin, Oily Acne Prone and Prone skin in general.

![bigrams](https://github.com/aychziel/K-Beauty-vs-American-Skincare/blob/main/plots/common_frequent_bigrams_koreanskincare_subreddit.png) 

For the the Korean skincare subreddit some information that was found was that...

The top written about products included
- cosrx snail mucin, Lab birch  juice, La Roche Posay, skin1004 madgascar centella.
  
Top written about skin concerns include 
- acne, oily acne prone, dry sensitive skin, sensitve acne prone, skin care routine.

Lastly, unique words only seen in the Korean skincare subreddit include
- water based cleanser, rice toner, anua heartleaf,  snail mucin essence,  skin barrier, and "started using".
---
#### Modeling ###

I tried different models like Logistic Regression, K-Nearest Neighbors, Random Forest Classifier, and Naive Bayes with Count Vectorizer and Tfidf. I found that using Naive Bayes with stop words gave the best precision score of 79%, surpassing the baseline accuracy of 50%. Logistic Regression with tuned hyperparameters achieved a precision of 76%.

---
#### Executive Summary, Conclusion & Recommendations ###

The main objective of this project was to identify the unique characteristics of K-beauty compared to American skincare. To achieve this, we classified both the Korean skincare subreddit and the SkincareAddiction subreddit. We examined the data and considered various classification models such as Logistic Regression, KNN, and others.

One of the standout factors was the use of "natural" and innovative skincare technology in K-beauty, which includes unique ingredients like rice and snail mucin. Additionally, specific discussions about skin products such as water-based cleansers and toners were prevalent. Moreover, the focus on prevention was evident in the Korean skincare subreddit through discussions about skincare prevention.

---
#### Limitations ###

Some of the limitations of this analysis include the need to review more Korean texts in my data in order to increase my score. I would like to try applying grid search with my top model. Additionally, I aim to use more feature engineering with the summary statistics. Implementing sentiment analysis on my data would provide more insight into the top brands found between both subreddits and allow for a more in-depth comparison of Korean products and American-based products. This implementation can help distinguish between American and K-beauty differences and can also be useful for future marketing analysis, including clustering and gauging opinions.
