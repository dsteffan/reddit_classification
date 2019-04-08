# DnD and Pathfinder Reddit Classification
---

### Introduction

For this classification analysis, the subreddits chosen were r/DnDNext and r/Pathfinder_RPG. These were chosen because they are for two tabletop roleplaying games that are very similar in terms of content and mechanics, but have some distinct similarities that make them unique. To properly classify them, steps must be taken in order to emphasize the differences rather than the similarites between them. 

### Problem Statement:

> How can we assess the and classify the topics between two highly similar topics while avoiding the particular language and patterns that form in one specific subreddit? 

This problem manifests mainly as variance between model scores. The reason for this is that models in NLP are highly susceptible to high variance, especially when using bag-of-words models. The patterns we want to avoid overfitting to are html artifacts from posted links, and threads that are automatically generated weekly or even daily by auto moderators. These two issues are specific to the subreddit and are not indicative of the actual topic of the subreddit. Most of the former can be addressed by adding the nonsense words in question to the list of stop words, but the latter is a bit harder to deal with as they often contain words that are relevant to the topic of the subredit. 

To answer this problem, a selection of classification models were used to model the data. As previously stated, the issue with most of these models is the high variance. To alleviate this issue, hyperparameter tuning via grid search was used to get to an acceptable baseline. After hyperparameter tuning started giving diminishing returns, count vecortors were utilized to reduce the amount of features overall.

### Conclusions

The model does a good job of predicting across the same subreddit with a consistent accuracy score in the lower 80s. The model also generalizes well to other similar subreddits, with an accuracy score in the upper 60s. While this is not an amazing accuracy score, the fact that it scores 18 percent above the baseline of 50 percent is significant for a model trained off of a simple bag of words. To further refine the model, extra scraping of both the default and alternate subreddits would be ideal, as well as a more robust way to isolate and eliminate the common features. 