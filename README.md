
# Movie Recommendation System using Auto-Encoders

####  - Project Description 
This project proposes an auto-encoder approach for producing a collaborative filtering system which
predicts movie ratings for a user based on what other similar users have rated. Using the Movie-Lens
1 million dataset, we explore the use of auto-encoder for predicting users’ ratings on unseen movies,
thereby enabling recommendation of movies. To verify and evaluate our approach, we compare our
approach to standard collaborative filtering technique like Spark ALS matrix-factorization.

####  - Introduction
The project is based on building a recommendation system using Auto-Encoders. Although generic
recommendation system have been around for quite sometime now, using auto-encoders for recom-
mendation system is a novel idea. Since every user does not watch or rate every movie, there are
a lot of missing data points in these massive datasets which makes them quite sparse. Data-sets
with 10k movies on an average have 50-300 ratings per user. This makes it really difficult to use
generic models. On the other-hand, auto-encoders learn the representation of the input data and
try to regenerate the same as the output. As there are a lot of missing input values (0 rating), the
auto-encoder anticipates and generates a rating for those movies which the user hasn’t seen based on
collaborative filtering.

####  - Method
The dataset used for our work is the 1 million and 20 million ratings dataset[5]. To evaluate our results, we compare matrix factorization performance
with auto-encoders. Spark implements alternative least squares (ALS) algorithm which is based on
matrix factorization[6]. 

In collaborative filtering approach, the user’s interests are predicted based on the analysis of other
users implicitly inferring “similarity” between them. The assumption is that two people who have
similar ratings, have a higher likelihood of having the same opinion on an item than two randomly
chosen people. 

Auto-encoders are a form of unsupervised learning algorithm, meaning that an auto-encoder only
needs unlabelled data, which means a set of input data is required rather than input-output pairs.
For linear reconstructions,the autoencoder attempts to learn a function that minimizes the root mean
square difference. Note that the RMSE decreases to 0 when the predicted values and the target values
are exactly same. On the other-hand, the error increases when the Euclidean distance between the
predicted values and the target values increases. The aim of using this approach is not to compute
an identity function, but to predict the missing ratings and not reproduce the zeros present in
the input vectors. The network is actually trained using a loss function for regression (i.e., RMSE)
with the aim of learning to predict missing ratings.

RMSE and MAE are two performance metrics widely-used for evaluating rating predictions on
multimedia data. Both RMSE and MAE measure the average magnitude of error, i.e., the average
prediction error, on incorrectly assigned ratings. The learnt model can then be used on the test
dataset for predicting the anticipated ratings that the user would have given. If the predicted
output matches the target values from the test set, then the autoencoder has learnt the under-
lying data-representation from the training set and generalized really well. This can be used
for recommending movies for users with similar tastes on unrated movies.
We explore the effects of using different activation functions and compared some of the common
choices : sigmoid, rectified linear units (relu), hyperbolic tangent (tanh), scaled exponential linear
units (selu) and linear.

####  - Conclusion
In this project, we demonstrated how deep auto-encoders can be successfully trained with and without
tied weights. Even on relatively small amounts of data, the tied weights with TANH had the lowest
RMSE of 0.67. Its loss is also lower than that of the spark ALS algorithm which is 0.81 and trained on
20 million ratings ,whereas we train the auto-encoder only on 1 million ratings. This concludes
why auto-encoders can be used for building recommendation systems over traditional approaches
even on smaller datasets.
