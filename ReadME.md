# Building a Recommender System

## 1. Summary 

The goal of this project is to build a recommendation engine for the users. In this context, there are plenty of different ways to build this engine. It might depend on the user habits, contents or genres. 

In order to build that engine, I benefit from the movie data set from the webpage [Kaggle](https://www.kaggle.com/rounakbanik/the-movies-dataset). This is a detailed dataset about movies, users and their ratings to each movie. Depending on the scale of the projects, there are smaller or larger datasets. 

To evaluate my model, I didn't use traditional metrics. It was only manual check for the movies and the suggestions. Not using a supervised model, made the evaluation process a bit harder but logical interpretation of the suggestions played a bigger role.

When building my model, I was also restricted by the limitations of the data given by Kaggle.com. For instance, the way data is stored resulted in big amount of time spent in the reshaping the tables.

## 2. Data

The data that I used included below CSV files. They are all available under the link provided above.

- credit: contains cast and crew information for all movies in the movies_metadata.csv file. 
- keyword: contains keywords for all the movies in the movies_metadata.csv file
- links: Contains IMDB and TMDB IDs of all movies featured in the ratings.csv file (About 45,000 movies).
- links_small: Contains IMDB and TMDB IDs of all movies featured in the ratings.csv file (For the smaller portion).
- movies_metadata: Contains Casd Crew Information for all movies in the movies_metadata.csv file.
- movies: CSV file created after the second notebook
- ratings: Contains Cast and Crew Information for all movies in the movies_metadata.csv file.
- ratings_small: Contains 100 ratings from 700 users on 9,000 +91 88708 42439. Is a subset of the ratings available in the Full MovieLens dataset.

## 3. Recommender Systems:

### 3.1 Basic Recommender

IMDB uses a weighted rating formula for the movies. This formula is very helpful in order to understand the actual ratings of the movies. Thanks to the below calculation we also take into consideration the amount of reviews on the movie. 

(WR)=(v/(v+m))R+(m/(v+m))C

- R = average for the movie (mean) = (Rating)
- v = number of votes for the movie = (votes)
- m = minimum votes required to be listed in the Top 50 (currently 1000)
- C = the mean vote across the whole report 

Utilizing this formula, we can calculate a weighted rating for each movie. After sorting them from the highest to lowest WR, we end up with the best movies per genre.

### 3.2 Content Based Recommender

Another recommendation is built using the movie descriptions. From each description, I used TF-IDF to check the words creating bins. At the end, I was able to recommend movies depending on the descriptions. 

When we think about this approach, it is a more detailed recommendation on just suggesting from a variety of genres. When we assume that the descriptions are summaries of each movie without giving away the key concepts, we can actually get a better sense of the similarities utilizing this information.






















