# Song Recommender (with Spotify Data)
![Spotify Banner](img/spotify-banner.jpeg)

## Update In Progress (Oct. 2023)
As this project is over 3 years old, I will be updating the code and README. 


<i> The version of the SpotifyFeatures.csv dataset originally used in this project is no longer available. Link to new dataset can be found [here](https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks?select=tracks.csv).</i>

## Introduction
In 2019, I have listened to 120,000+ minutes worth of music, which can be converted to 2,000 hours and 83.3 days. So I do consider myself a huge music enthusiast and enjoy exploring new music. 

I am also a fan of Spotify's amazing recommendation system and I watned to create a "poor man's" version of it, and see if I can discover any new hidden gems through my version. 

## Problem Statement 
Create a song recommender using personal Spotify listening history and song features provided by Spotify to classify a song as 'Liked' or 'Not Liked'.

## Data 
### StreamingHistory.csv
Personal Spotify listening history obtained through Spotify through a JSON drop. 
### SpotifyFeatures.csv
Dataset with 223,044 songs with song features such as popularity, key, valence, and more. This data was downloaded from Kaggle. 

All songs in Spotify have song features that describe the audio numerically that range from 0 to 1. For example, the <i>valence</i> feature with a value of 1 measures the song as very happy, while a value of 0 states the opposite. 

With these values, I can explore if I prefer certain song characteristics more than others (e.g. happy vs sad music). This is how we will recommend songs by identifying features with the highest correlations to our favorite songs. 

## EDA


## Modeling
* Logistic Regression
* Decision Trees 
* Random Forest

## Model Evalution 
### F1 Score
A high F1 score indicates that the model is good at identifying both positive and negative cases, which is important to minimize the model classifying a bad song as a song that I would 'like' and maximize the model classifying a good song as a song that I would 'like'.

In other words, it enables us to take into account false negatives and false positives when calculating the accuracy of the model. In constrast, if we use accuracy, false positives would be considered as correct predictions which is misleading. 

#### Defining our prediction variable
Our prediction variable will be called "favorite" with 1 representing a well-liked song and 0 representing otherwise.
But, what is a 'favorite' song? I decided to label songs with more than 15 listens as a favorite and those with less as not. 

Why 15? When I plotted the song counts on a histogram, there was a substantial drop in song frequencies after 15. These cutoff seemed like a perfect place to differentiate songs that I casual listen to versus songs that I truly enjoy. 

![favorite](data/favorite.png)

### Conclusion, Results and Actionable Next Steps
![Recommendations](data/recommendations.jpg)

I was able to train a Logistic Regresssion model with a F1 score of 86% on unseen test data. The RandomForest model came in close at 84% while the DecisionTrees model was last at 73%. 

Moreover, this project has enabled me to obtain a mass recommendation of songs at once instead of having to go through options such as Discover Weekly (limited to 30 songs), look through different playlists, or opt for a playlist radio.

This project has also created two actionable next steps. First, I created a script that enables me to automate playlist creations by converting .csv recommendation files into a Spotify playlist. 
* Link to that script can be found here: https://github.com/isacmlee/csv-to-playlist.

Second, I have also productionized a version of this model at http://www.whatspopping.xyz/. If curious, please give it a try! :)
