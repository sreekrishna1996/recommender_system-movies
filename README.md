## recommender_system-movies

### Business Case: Zee Recommender Systems

#### Problem Statement:

Create a Recommender System to show personalized movie recommendations based on ratings given by a user and other users similar to them in order to improve user experience.

#### Solution: EDA | Buidling Recommendation Systems

ZEE is an Indian subscription video on-demand and over-the-top streaming service As per the business problem, business team wants a Recommender System created to show personalized movie recommendations based on ratings given by a user and other users similar to them in order to improve user experience.

3 Data frames were provided which had information of users and their characteristics, movies along with genres and users ratings for different movies along with timestamps.  Not much preprocessing was required as the data frames were simple and straight forward. Missing values were imputed and incorrect entries were corrected.

With the help of given data, I was able to build multiple recommender systems, which can help recommend movies to a user based on their interests/watch history.

1. For EDA purposes, I only used count plots as all my features were categorical. All my Insights from each and every plot have been mentioned in my Jupyter notebook.
2. Depending on the system I was building, I feature engineered new variables like Avg-rating, release year etc. and merged more than 1 data frame to build a system which is as strong as possible.
3. After preprocessing all the 3 data frames, firstly, I built a Content based recommender system using Pearson Correlation. I wrote a custom function, which takes the movie as input and then calculates its correlation with all the other movies and recommends the top 5 movies with the highest correlation. The top 5 movies are sorted based on the the avg-user rating of each movie. Instead of just recommending movies based on the correlation coefficient value, I also used the avg-user ratings to improve my recommendations. If space is not our constraint, we can directly deploy the already calculated recommendations data frame on the server to save time. 
4. Secondly, I built recommender systems based on Cosine Similarity. After scaling the features, I built user and item similarity matrices with had values of cosine similarities among different movies and among different users. We can use the data from these matrices to recommend top users and top movies. 
5. Finally, I used the Matrix Factorization method to build a user-item based recommender system. Gradient decent algorithm was used to get the user and item embeddings consisting of 4 features. I tuned my hyperparameters using RMSE and MAPE scores. I could achieve an RMSE value of around 1.117 and MAPE score of around 0.38. This system was built using the cmfrec library. We can use the topN attribute to recommend movies that a user might like on the basis of reactions by similar users.
6. I also used the same embeddings instead of original features to build item-item similarity and user-user similarity matrices. I found that item-item similarity recommendations were good with embedded features. Even though recommendations using original and embeddings were comparatively different to one another, all the recommendations combined were quite similar to the actual movie. User-User similarity recommendations using embeddings were not accurate. Infact, I found them to be very bad. We can just stick with the original features for accurate recommendations. 

To whoever reads this, I hope my insights and recommendations from this case study were meaningful.

Thank you,

Krishna
