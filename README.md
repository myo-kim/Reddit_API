
# Project 3 Reddit API

### Problem Statement

Looking to learn about stock trading and different stock trading strategies? You might want to head over to reddit to see if there are existing subreddits solely dedicated to talking about stocks. Much to your advantage, there are a variety of subs dedicated to trading and different methodologies (forex, options, using robinhood specifically, weed stocks, etc). But where do you begin and how should you filter through the vast amount of information?  

Two very informative places to start are r/Stocks and r/Investing. However, you're a very busy person who doesn't have much time to be looking at **both** of these subreddits. These subreddits seem very similar, but on first glance, are you able to tell? Do you need to read both subreddits in order to be a well informed trader?

---

### Datasets

The datasets utilized were:

- [r/Stocks Data](./data/stocks_data.csv)
- [r/Investing Data](./datas/invest_data.csv)

### Data Description

Each column represents an individual unique word found in the title of each post. If the word was found in the title it is marked with a 1 and 0 if not.

---

### Executive Summary

The two subreddits are very similar, from their names to their descriptions. r/Stocks is described as a place to talk all things stocks, be it buy/sell suggestions, tips, economic news, etc. r/Investing is not much different except it includes jargon about technical analysis. The model works to separate the two subreddits by their title only. 

The posts collected are almost evenly split, with r/Stocks making up 44% of the entire dataset and r/Investing making up 56%. There is a total of 1,687 posts collected. I ran through a variety of models in order to see how each model compared to the baseline. However, the accuracy score for the models were quite similar and did not do much better than the baseline accuracy. 

Although it could be a problem with the models themselves, I believe that these two subreddits content wise are not very different.

---

### Methodology

The first step was to collect the data from the subreddits. In order for the model to train with a balanced data set, I aimed to collect close to 1,000 posts from each subreddit. r/Stocks had a collection of 743 posts while r/StockMarket had a collection of 944. The combined dataset did not have a clean split between the two but was close enough for the model to work off of. 

To clean the data, repeated posts were removed based on their post names. Daily Discussion or Daily Question threads were removed as well. In order to work with a smaller number of features, the model only evaluated post titles. Even then, the total word count was 3,209 (using ngram (1,1)). The texts were split into features using either Count Vectorizer or TF-IDF Vectorizer. The models utilized were Logistic Regression, Multinomial Bayes, Decision Trees and Bagging. GridSearch was used to find the best parameters for the vectorizers and models. 

The model that was the most accurate was the Multinomial Bayes using TF-IDF vectorizer. The baseline accuracy was 55% and the model scored 64%. 

**Visualizations**  
The graph for the scatter plot using text was created using a library called Scatter Text created by Jason Kessler. The graph works to plot the frequency of words for both subreddits, each subreddit having an axis.  

The graph for the co-occurence of words was created using Gephi.

---

### Conclusion and Next Steps 

As the accuracy score did not vary greatly from the varying models, it can be inferred that the posts between the two subreddits are too similar to accurately split into different categories. Therefore, it is recommended for new investors to focus on one subreddit rather than read both. 

However, as the model only focuses on the title of the posts and not text, the investor should look into what content they are specifically looking for. It seems as though the topics (based on titles) covered in the two subreddits are very similar. This does not directly correlate to the commentary or content of the posts. Therefore, while the topics talked about might be similar, there could be different commentary based on the subreddit. 

While the time sensitive investor might choose to focus on only one subreddit, to get a broader breadth of information it would be beneficial to stil read both subreddits. 

---


