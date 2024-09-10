# What characteristics make K-beauty unique compared to American skincare brands?
#### Problem statement :

The skincare industry in the United States is experiencing unprecedented growth, driven by increasing consumer awareness, advancements in product formulations, and the rise of e-commerce ([Source](https://illuminationconsulting.com/2024/06/25/)).

An American skincare company called "AK" is looking to integrate Korean skincare in their line as the company changes to be American-Korean based. Their mission as a company is implementing the latest in skincare technology in their products. As of now, the company is seeking and effective way to classify their skin care products in their system to find what products belong to the American versus the Korean. By creating a classifier modeling system that has a high score in comparison to our baseline data, we would not only be able to classify the products but also, obtain strong findings to help market the Korean skin care implementation in the new American Market sector most effectively. 

The goal of this project: (1) Build a classification model that can accurately classify the Korean from the American products. (2) Offer recommendations and insights on the main differences and share findings to help support marketing decisions to support the mission of the company.

---

### Datasets ###
Background on data: The following data was obtained from scraping the Skincare Addiction subreddit and the Korean Skincare subreddit on Reddit. 

Skincare Addiction is a subreddit where users discuss skin care concerns, product recommendations, opinions of ingredients, and more. The Korean skincare subreddit is a similar community to the Skin Care Addiction where they discuss similar general topics, however, the Korean skincare subreddit is known to discuss more about Korean-based skin care products, ingredients and the industry but not exclusive to all skincare products. 

The Skincare addiction subreddit has a significant amount of American users which is why the subreddit would help compare. As for the Korean skin care Reddit, there is a combination of Korean and American users. 

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

As I identified the data, I took appropriate measures by using count vectorization, testing whether to use lemmanization or tokenization etc ![word cloud](https://github.com/aychziel/K-Beauty-vs-American-Skincare/blob/main/plots/word_cloud_eda.png). I also tried to remove korean text for the purpose of this analysis.

#### Modeling ###
I tried a variety of models including Logistic Regression with with Count Vectorizer, Tfidf, K-Nearest Neighbors, Random Forest Classifier, and Naive Bayes. To preprocess the text, I used Count Vectorizer with few restraints(max features, stop words). Most of the limitation came from the stop words. This affected the accuracy, however made the information more useful.

I found that utilizing multinomial Naive Bayes model, with default parameters was the best model as it had a precision score of 79% and was higher that the baseline accuracy score which was approximatley 50%. I achieved this by implementing stop words and getting rid of noise(cleaning) in the data. I also used grid search and tuned hyperparameters for my Logistic Regression model which was 76%. 

I was also able to determine that there was 53 false postives and 56 false negatives in my misclassified posts with my Logistic regression model. With the feature importance, I found that there was many distict words that were important to post data that may be realted mostly to skin concerns. The reason for this I believe is because both subreddits are used alot for gauging opinion and the text data matched with diction that pertains to this.

#### Executive Summary, Conclusion & Recommendations ###

The purpose of this project was to find what characteristics make K-beauty unique compared to American skincare? To do this, we needed to classify both korean skincare subreddit and the skincare addiction subreddit using the two subreddits, the skincare addiction subreddit and the korean skincare subreddit. To do this, we needed to explore the data and which classification models to apply such as Logistic regression, KNN and more. 

After deciding what data to use, I began to research to formulate my hypothesis with the data. Based on my research, my hypothesis was that Korean skincare was unique because of the ingredients that were used. In my data cleaning process, I took the three data sets that I had, and identified null values, data types, variable names, missing text data and removing language barriers.

In summary, the answer is that there are many factors, but the main ones that stood out are Korean skincares use of "natural" and innovative skin technology that includes implementing unique ingredients such as rice and snail mucin and specific discussion of types of skin products such as water based cleansers, toners etc. They also focus on prevention as there was discussion about skin care prevention in the korean skincare subreddit.

Some findings were that.. 

- The top written about Brands included Beauty of Joseon, La Roche Posay, and cosrx.

The Top written about Ingredients include 
- Snail Mucin, Cleansing oil, Hyaluronic Acid and Salicylic Acid.

Finally the Top written about skin concerns include 
- Acne Prone, Dry Skin, Sensitive skin, Oily Acne Prone and Prone skin in general.

It was found that Although there was alot of overlap in the skincare addiction subreddit there is more discussion on brands and less on "natural" skin care ingredients.

For the the Korean skincare subreddit some information that was found was that the top written about products included
- cosrx snail mucin, Lab birch  juice, La Roche Posay, skin1004 madgascar centella.

Top written about skin concerns include 
- acne, oily acne prone, dry sensitive skin, sensitve acne prone, skin care routine.

Lastly, unique words only seen in the Korean skincare subreddit include
- water based cleanser, rice toner, anua heartleaf,  snail mucin essence,  skin barrier, and "started using".

Based on my findings, my recommendation is that utilizing multinomial Naive Bayes model, with default parameters will best help classify K-beauty and American skincare and can be used to support marketing initatives to better target customers.


### Limitations ###

Some of the limitations to this analysis include reviewing more Korean Text in my data to increase my score and applying grid search with my top model. I would also use more Feature Engineering with the summary statitics. I would also implement Sentiment Analysis on my data to get more insight on top brands I found between both subreddit and compare Korean products and American-based products in depth. Lastly,  Implementing this can not only help differentiate between the American and K-beauty diffrences, but can also be useful for future analysis in marketing through clustering, gauging opnion and more! 
