# DrugReviewAnalysis
ML analysis on Drug Reviews to find trends


Please just make a copy of this notebook to your own driveto avoid out-of-sync changes!

This is just a template!

<a target="_blank" href="https://colab.research.google.com/drive/1uRc9exMVVDasgsu6Yi3IU7UYbOXq4Qvy?usp=sharing">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# Next Steps

We will conduct sentiment analysis on user reviews for birth control drugs in order to predict user ratings and screen drugs for things like effectiveness and side effects. To conduct sentiment analysis, cleaning of the data will be necessary. Cleaning measures include:
* reducing redundancy (lowercasing, replacing contractions, stemming, lemmatization)
* tokenization ('i will find you' -> ['i', 'will', 'find', 'you']
* removing punctuation, stopwords, special characters
* assigning parts of speech to words
* spellcheck
We will also need to assign sentiment values to words. For instance, "great" may be assigned a more positive value than "good", and "bad" will be assigned a negative value.

# Milestone 3

1. Finish major preprocessing

2. Train your first model
   
3. Evaluate your model compare training vs test error

4. Where does your model fit in the fitting graph?
* We created two models, a basic linear regression using TF-IDF and a Decision Tree Regressor. When evaluating the models, we looked at the mean squared error after fitting the data. Additionally, we also chose to look at the accuracy since the problem we are trying to solve, predicting the rating based on the dataset, could also rather easily be interpreted as a classification problem rather than the regression problem as we intend to examine with our project. While the linear regression model was not complex enough to have a good error or a good accuracy, the decision tree model overfit on the dataset.

5. What are the next 2 models you are thinking of and why?
* We are thinking of a feed-forward Deep Neural Network. Then, we are also thinking of doing a CNN/LSTM model next. We hope to use more complex models so that the we can better learn on the text data without overfitting. However, we will be looking in to what kinds of models are better suited for natural language processing, so the current plan may change as we look into more avenues to experiment with.
  
6. Update your readme with this info added to the readme with links to the jupyter notebook!

7. Conclusion section: What is the conclusion of your 1st model? What can be done to possibly improve it?
* From these first basic models, it is clear that this problem is something that is not easily solved with a basic model, given the lack of success with our linear regression model. But with the lack of success due to overfitting with the decision tree model, arbitrarily creating complex models will likely still fail to accurately predict what we want.

**Preprocessing Notebook**
<a target="_blank" href="https://colab.research.google.com/drive/1EMYviqbrdtww675lYtezEbsQQaurpzNl?usp=sharing">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

**First Models Notebook**
<a target="_blank" href="https://colab.research.google.com/drive/1zk3EfA1TB6yLUie8NPrlloXDgEvlUPzD?usp=sharing">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# Milestone 4

1. Evaluate your data, labels and loss function. Were they sufficient or did you have have to change them?
   * The first model we used was a linear regression using MSE for loss. We decided to not make any changes in our data or our targets. For this milestone, we will use a DNN with MSE as our loss function.

3. Train your second model

4. Evaluate your model compare training vs test error
   * We had a training mean squared error of 6.408446640685858 and a test mean squared error of 9.6741797.

6. Where does your model fit in the fitting graph, how does it compare to your first model?
   * Our model is not as good as our first model, as the test error of our first model was 6.32, and the test error of this model was 9.6741797. Thus, while it doesn't overfit as severly as the decision tree regressor model from our previous milestone, it still seems to be overfitting.

8. Did you perform hyper parameter tuning? K-fold Cross validation? Feature expansion? What were the results?
   * We performed feature expansion by doing sentiment analysis on the review texts on top of TF-IDF. Additionally, we tried optimizing our model through adjusting the number of nodes in our dense layers. Neither linear regression nor DNN was significantly improved by these choices as compared to our previous model.

5. What is the plan for the next model you are thinking of and why?
   * For our next model, we are planning on using context-dependent word embedding instead of TF-IDF. This is because we have not seen significant improvement by simply increasing the complexity of the model. We want to try changing the main way we are processing the text data, the most crucial feature of our inputs, so trying a new embedding method may show better results. Especially since our rating does depend on the context of the reviews, so we believe that experimenting with a context-dependent word embedding like BERT may lead to improvements in our model.

7. Update your readme with this info added to the readme with links to the jupyter notebook!

8. Conclusion section: What is the conclusion of your 2nd model? What can be done to possibly improve it? How did it perform to your first and why?
   DNN and feature performance did not significantly improve our error, though it did prevent overfitting. We are hoping ot improve on performance by using a different word embedding from TF-IDF for our next model, such as context-dependent word embedding.

Please make sure your second model has been trained, and predictions for train, val and test are done and analyzed. 
