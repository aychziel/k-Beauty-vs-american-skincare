# What characteristics make K-beauty unique compared to American skincare brands?
#### Problem statement:

An American skincare company called "AK" is looking to add Korean skincare in their line as the company changes to be American-Korean based. Their mission as a company is implementing the latest in skincare technology in their products. As of now, the company is seeking an effective way to classify their skin care products in their system to find what products belong to the American versus the Korean and how they can better differentiate their new products for marketing purposes.

The goal of this project: (1) Build a classification model that can accurately classify the Korean from the American products. (2) Offer recommendations and insights on the main differences and share findings to help support marketing decisions to support the mission of the company.

---

### Datasets ###
Background on data: The following data was obtained from scraping the Skincare Addiction subreddit and the Korean Skincare subreddit on Reddit.Skincare Addiction is a subreddit where users discuss skin care concerns, product recommendations, opinions of ingredients, and more. The Korean skincare subreddit is a similar community to the Skin Care Addiction where they discuss similar general topics, however, the Korean skincare subreddit is known to discuss more about Korean-based skin care products, ingredients and the industry but not exclusive to all skincare products.

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

As I identified the data, I took appropriate measures by using count vectorization, testing whether to use lemmanization or tokenization. I also removed some korean text for the purpose of this analysis. ![word cloud](https://github.com/aychziel/K-Beauty-vs-American-Skincare/blob/main/plots/word_cloud_eda.png) 

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

#### Modeling ###
I tried a variety of models including Logistic Regression with with Count Vectorizer, Tfidf, K-Nearest Neighbors, Random Forest Classifier, and Naive Bayes. To preprocess the text, I used Count Vectorizer with few restraints(max features, stop words). Most of the limitation came from the stop words. This affected the accuracy, however made the information more useful.

I found that utilizing multinomial Naive Bayes model, with default parameters was the best model as it had a precision score of 79% and was higher that the baseline accuracy score which was approximatley 50%. I achieved this by implementing stop words and getting rid of noise(cleaning) in the data. I also used grid search and tuned hyperparameters for my Logistic Regression model which was 76%. 

#### Executive Summary, Conclusion & Recommendations ###

The purpose of this project was to find what characteristics make K-beauty unique compared to American skincare? To do this, we needed to classify both korean skincare subreddit and the skincare addiction subreddit using the two subreddits, the skincare addiction subreddit and the korean skincare subreddit. To do this, we needed to explore the data and which classification models to apply such as Logistic regression, KNN and more. 

I foudn that the main factors that stood out were Korean skincares use of "natural" and innovative skin technology that includes implementing unique ingredients such as rice and snail mucin and specific discussion of types of skin products such as water based cleansers, toners etc. They also focus on prevention as there was discussion about skin care prevention in the korean skincare subreddit.


### Limitations ###

Some of the limitations to this analysis include reviewing more Korean Text in my data to increase my score and applying grid search with my top model. I would also use more Feature Engineering with the summary statitics. I would also implement Sentiment Analysis on my data to get more insight on top brands I found between both subreddit and compare Korean products and American-based products in depth. Implementing this can not only help differentiate between the American and K-beauty diffrences, but can also be useful for future analysis in marketing through clustering, gauging opnion and more! 
