# What characteristics make K-beauty unique compared to American skincare brands?
# Problem statement:
AK is an American skincare company that is looking to integrate Korean skincare in their line as the company changes to be American Korean based. Their mission as a company is implementing the latest in skincare technology. As of now, the company is seeking to classify their skin care products and needs help in finding effective ways to do so in their Skin Care database in a particular way that is able to determine what products belong to the American versus the Korean. Our goal as data scientist is to find the most effective way to classify skin care products and potentially find ways to use this to help market their Korean Skin Care in the American sector of the company. By creating a classifier modeling system that has a high score in comparison to our baseline data, we would be able to not only organize the products but also potentially help Market the Korean skin care implementation in the new American Market sector. 

---

### Datasets ###
Background on data: The following data was obtained from Reddit, specifically the Skincare Addiction Subreddit and the Korean Skincare subreddit. Skincare Addiction is a subreddit where users discuss skin care concerns, product recommendations, opinions of ingredients, and more. The Korean skincare subreddit is a similar community to the Skin Care Addiction where they discuss similar general topics, however, the Korean skincare subreddit is known to discuss more about Korean-based skin care products, ingredients and the industry but not exclusive to all skincare products. 

The Skincare addiction subreddit has a significant amount of American users which is why the subreddit would help compare. As for the Korean skin care Reddit there is a mix of Korean and American users. 

---

### Data Dictionary ###


|Feature|Type|Dataset|Description|
|---|---|---|---|
|**created_utc**|*object*|Reddit|Data converted to UTC| 
|**title**|*object*|Reddit|Post titles from reddit|
|**self_text**|*object*|Reddit|Posts|
|**subreddit **|*object*|Redit|Which subreddit, Korean skincare or skincare addiction|


---

#### Executive Summary And Recommendations


The purpose of this project was to find a way to answer the problem statement question, What characteristics make K-beauty unique compared to American skincare? To do this, we needed to classify both korean skincare subreddit and the skincare addiction subreddit using the two subreddits, the skincare addiction subreddit and the korean skincare subreddit. To do this, we needed to explore classification models such as Logistic regression, KNN and more and go through the NLP process as well. 

After deciding what data to use, I began to research to formulate my hypothesis with the data. Based on my research, my hypothesis was that Korean skincare was unique because of the ingredients that were used. In my data cleaning process, I took the three data sets that I had, and identified null values, data types, variable names, and missing text data. As I identified the data, I took appropriate measures to clean it by replacing, using count vectorization, testing whether to use lemmanization or tokenization etc. 

In summary, the answer is that there are many factors, but main ones that stood out are Korean skincares use of "natural" and innovative skin technology that includes implementing unique ingredients such as rice and snail mucin as discovered in the EDA process and more use /discussion of specfic types of skin products such as water based cleansers, toners etc. They also focus on prevention as there was much talk about skin care prevention in the korean skincare subreddit. To summarize the EDA for both skincare reddits some intresting findings were that the top written about Brands included Beauty of Joseon, La Roche Posay, and cosrx. The top written about Ingredients include Snail Mucin, Cleansing oil, Hyaluronic Acid and Salicylic Acid. Finally the Top written about skin concerns include Acne Prone, Dry Skin, Sensitive skin, Oily Acne Prone and Prone skin in general. It was found that Although there is alot of overlap in the skincare addiction subreddit there is more discussion on brands and less on "natural" skin care ingredients.

For the the Korean skincare subreddit some information that was found was that the top written about products include cosrx snail mucin, Lab birch  juice, La Roche Posay, skin1004 madgascar centella. Top written about skin concerns include acne, oily acne prone, dry sensitive skin, sensitve acne prone, skin care routine. Lastly, unique words only seen in the Korean skincare subreddit include, water based cleanser, rice toner, anua heartleaf,  snail mucin essence,  skin barrier, and "started using".

In the modeling process, I decided to choose my models based off the NLP process. I found that utilizing multinomial Naive Bayes model, with default parameters would best help classify K-beauty and American skincare with a score of 78% accuracy and was higher that the baseline accuracy score which was approximatley 50%. I achieved this by implementing stop words and getting rid of noise in the data. I also used grid search and tuned hyperparameters for my log reg model with was 76%. I was also able to determine that there was 53 false postives and 56 false negatives in my misclassified posts with my Log reg model. With the feature importance I found that there was many distict words that were important to post data that may be realted mostly to skin concerns. The reason for this I believe is because both subreddits are used alot for gauging opinion adn the text data matched with diction that pertains to this.

Based on my findings, my recommendation is that utilizing multinomial Naive Bayes model, with default parameters will best help classify K-beauty and American skincare and can be used for further marketing exploration.


Limitations

Some of the limitations to this analysis include reviewing more Korean Text in my data to increase my score, and using Grid Search in my top model. I would also use more Feature Engineering with the summary statitics. I would also was to implement Sentiment Analysis on my data to get more insight on top brands I found between both subreddit and compare Korean products and American-based products in depth. Lastly,  Implementing this can not only help differentiate between the American and K-beauty diffrences, but can also be useful for future analysis in marketing through clustering, gauging opnion and more! 
