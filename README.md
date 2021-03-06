# Netflix-Recommendation-System
Here, I am trying to make different types of recommendation Systems on Netflix Data which is published as a part of the competition 2 years back.
So first of all, let me mention that the data is a bit large, that is 2 Gb and contains about 10 crores of ratings by different users on the Netflix TV shows and movies.
Training part was the most hectic one in this project and if you are working on this project and doesn't have much hardware resources  i suggest you to load much lesser data to work.

# Dataset
As you can see in the code, there are 10,04,80,507 ratings outhere which is been given by 4,80,189 different viewers for 17,770 feature movies. The dataset is quite large and we have to use good hardware resources to work on it ,even with a tactical approach.The dataset is published as a part of the competition on Kaggle 2 years back. The link to the Dataset is given below.
https://www.kaggle.com/netflix-inc/netflix-prize-data
The dataset contains 4 particular infos namely Customer ID,Rating,Date of Rating,Movies ID(as the first line).
Our first motive is to extract these informations or data in a particular form in which we could work on it. The name of the columns have to be given explicitly.
Our major constraint out here is to load this much data by tackling the "Memory Error".

# Info regarding Recommendation Systems
Recommendation system creates a similarity between the user and items and exploits the similarity between user/item to make recommendations.
There are mainly 6 types of the recommendations systems :-
1) Popularity based systems :- It works by recommending items viewed and purchased by most people and are rated high.It is not a personalized recommendation.
2) Classification model based:- It works by understanding the features of the user and applying the classification algorithm to decide whether the user is interested or not in the product.
3) Content based recommedations:- It is based on the content of the item rather than on the user opinions.The main idea is that if the user likes an item then he or she will like the "other" similar item.
4) Collaberative Filtering:- It is based on the assumption that people like things similar to other things they like, and things that are liked by other people with similar taste. It is mainly of two types: a) User-User b) Item -Item
5) Hybrid Approaches:- This system approach is to combine collaborative filtering, content-based filtering, and other approaches .
6) Association rule mining :- Association rules capture the relationships between items based on their patterns of co-occurrence across transactions

# Logic behind Slicing the Dataset
We would love to work with the whole dataset outhere but since tha data is super huge we have to reduce it without compromising the quality. So we decided to eliminate the customers and feature films which are less active.

# Methodology
1) I loaded all the four text files and then merged it into a single dataframe. While loading all these, i named the columns. Here, we are neglecting the role of Date.
2) We are using pandas for dataframe working and all with numpy as a backup for manipulation. For data visualization, we use seaborn and matplotlib.
3) Since there exist NaN values only in the row of Movie ID specification, we acquire the movie count by extracting only those. Similarly by counting the unique Ids in CustomerId column, we got the total number of users without much trouble.
4) Then to visualize this data, we used matplotlib and made a horizondal bar diagram with percentage of corresponding rating value as subject.
5) For putting in the movie column, we use the numpy approach because we can't work with the conventional loop approach due to memory contraint.
6) The data will again reduced without compromising much on quality with the logic mentioned above.
7) After preparing the whole dataset as we wanted, we pivot it for sake of recommendation system. 
8) Then we map the Movie ID column with the mapping dataset.
9) Then we use the Singular Value Decomposition technique(SVD) for constructing Model Based Recommendation System.
10) After constructing a collaborative filtering recommendation system on user-user approach, we started to modify the data to built a popularity based recommendation model
11) We sorted the data on the basis of popularity for the sake of hybrid system.
12) After that a non probablistic model is built using "KNN" Concept.
13) At last , we made a item-item interactive recommendation system and made real time predictions based on Pearson's correlation

# Conclusion
As you can see at the end, we made a number of predictions by considering different logic to understand the efficiency of our system. We can see that when we try to recommend movies based on 'Forrest Gump', we could see more movies of TOM HANKS. This suggest that our model is understanding a pattern. Also, when we tried to predict some recommendations corresponding to a subject which has a prequel/sequel, we got those as the top most related, an another good sign. At last we had given a superhero movie as input and guess what, we got a number other superhero movies as recommendations. So with all these results, we could say that the model we built works pretty fine.




