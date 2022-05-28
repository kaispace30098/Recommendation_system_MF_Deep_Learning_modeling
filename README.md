# Recommendation_system_MF_Deep_Learning_modeling
This project is trying implement recommendation system with Keras API by collaborative filtering methods. The data we are training is The Movies Dataset at Kaggle(26 million ratings from 270,000 users for all 45,000 movies.)
https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset
The first model is a simple matrix factorization, which the ranking from user i to product j can be expressed as ui dot pj where elements u and p belong to decomposed user and product matrices.  The second model is a deep feed foward nueral network model where the inputs features are concatinated from user and product embedding matrices.For model evaluation, we use Tensorboard callback to plot out our metrics, in this case, Mean Sqaured Error. As a result, the DNN outperforms the traditional Matrix Factorization. 
![image](https://user-images.githubusercontent.com/93064471/170845237-82598bb5-506f-40cc-8f7b-18293c8615d7.png)


As a Machine learning practitioner, before dealing with larger datasets, we can train our model by smaller data, so the 'Most common data sampler' notebook is created.
In this notebook our goal is to sample the users with most movie rates intersect with the movies with most reviews from users.
1. We create a Counter dictionary to store each id of user as key and the count as value. so do movie.
2. We use most_commen function from Counter class to get the top n reviewers and top m movies with most reviews and use them as indecies
3. We select from all data only with users in top_user index and movies in top_movie index.
4. Because we want to keep the user id and movie id in seqential series. we re-create a dictionary where key is old user id as key and accumulator as value, apply to both extracted users and moives and put it back to the dataframe.
5. Output as a new datasets for further research.
