# Detection-of-Fake-News-Posts-on-Facebook
Detection of Fake News Posts on Facebook using R

In today’s social media obsessed world, it is quite uncommon to verify the authenticity of facts or news.
There have been innumerous case of fake news being shared and promoted for private propaganda. In this
project we have tried to determine the authenticity of the news posts on Facebook by using machine learning
algorithms to classify the news as false or true.

The dataset for this analysis is derived from a labelled dataset for Facebook news post by multiple news
agencies available on GitHub. Using the post ID and Facebook API (in R) we have collected the information
associated with each post. 

Our goal is to classify the posts using the post message, user comments and reactions on it.


## Data Collection and Processing

The original labelled dataset available on GitHub had more than 2000 unique post with class labels. However,
the proportion of each class in the dataset was highly biased. To overcome this limitation, we sample 288
unique posts containing 67 percent posts belonging to class labelled as true and 33 percent to false. Then this
data set was randomly partitioned into 30 percent test and 70 percent train dataset.

Comments for the each post are converted into 300 dimentional vectors. To determine the 300-dimensional sentiment of a post,
we used two approaches The first approach involved training the vectors on the comments corpus and for second approach a
pretrained vector on 3 billion words (on Mikolov’s word2vec skip gram model) from google news was chosen.

As the Ratio of no of predictors to observations is quite high ~ 1.5 and hence we decided to explore
machine learning techniques like Nearest Shrunken Centroid and Random Forest Machine Learning
Techniques. Since most of the 300 dimensional vectors were uncorrelated, we also explored the performance
using a Naive Bayes Classifier.


## Results

Random forest machine learning technique outperforms other method for prediction accuracy and
has higher area under the curve roc curve. This behavior can be explained because of low training observations
(201) and since trees in random forest are fully grown and not pruned which might coerce it to find a perfect
split till the very last node. 

Nearest shrunken Centroid method also gives good prediction results > 90 % and is a reliable technique used 
in high dimensional setting.

Naïve Bayes classifier perform poorly compared to other two techniques which are particularly better suited 
for high dimensional setting.

