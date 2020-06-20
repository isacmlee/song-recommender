## Building a Spotify Recommender based on Listening History and Song Features
You can find the project's notebook [here](https://nbviewer.jupyter.org/github/isacmlee/song-recommender/blob/master/song-recommender.ipynb).
### Introduction
Based on my Spotify Wrapped for 2019, I accumulated 120,000+ minutes of listening which translates to over 2000 hours, which also translates to a whooping 83.3 days. So I do consider myself a huge music enthusiast and enjoy exploring all the different genres music has to offer. Because of my extensive listening history, I realized I had a lot of data to work with to **create a classifier that will state whether or not I would like to listen to a song or not.**

### Goal
In this project, I will build a song recommender based on my personal Spotify listening history and a Spotify song features dataset (https://tinyurl.com/y7mpts3e). **To accomplish this, I will compare 3 classifier models: Logistic Regression, Decision Trees and Random Forest, and evaluate each model based on the F1 score and the runtime of each. In addition, I will be able to discover which song features appeal to my song preferences more.** 

The variable that I will be predicting will be a binary feature with 0 representing "not a favorite" and 1 representing a favorite. I will create this binary feature through my personal listening history and label songs with more than 15 listens as a favorite and those with less as "not a favorite". Why 15? When I plotted the song counts on a histogram, there was a drop in song frequencies around 15. I concluded that this would be a good cut off as songs past the cut off were clearly less in number than those before. There most be something about those songs that create this cutoff. As a result, I would be able to hone in on the features that makes a song a favorite more. 

### Steps
* Data Cleaning / Exploration 
* Balancing Classes with Oversampling (SMOTE) and Feature Selection
* Model Selection with Cross-validation and Hyperparameter Optimization
* Predicting Songs and Saving Dataset for Personal Use

### Conclusion / Results
Through this project, I was able to fit a Decision Tree Classifier with a F1 score of around 97%, confirmed through cross-validation as well as unseen test data. While the Logistic Regression model had the shortest computing time, it also had the lowest F1 score. On the other hand, Random Forest had the best F1 score with the highest computing time. The Decision Tree was a perfect tradeoff between time and F1 score as it was only 2% worse than Random Forest but only 30 seconds slower than Logistic Regression. 

I also discovered that the song features that had the most association with a favorite song of mine were popularity (+ association), danceability (+ association), and instrumentalness (- association). This finding indicates that my music taste is generally mainstream with good characteristics of a dance song but also with more focus on words. All these features appear to represent the Pop genre, which may indicate that is may favorite genre.

With these features and a hyperparameterized Decision Tree model, I was able to recommend songs that I would favorite and create a playlist with these songs. 
