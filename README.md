# rock-climbing-recommender
A rock climbing route recommendation system

### Abstract
The goal of this project was to provide recommendations on similar rock climbing routes based on a route the user inputs. I worked with the data on Mountain Project's website to obtain each route's statistics, location, and text descriptions. Through feature engineering and pairwise distance measurements, I was able to determine the most similar routes to a specified route based on each route's features. 

### Design
Mountain Project is the most popular application for rock climbers to find information about routes across the world. While this app contains pertinent information and is incredibly useful, it lacks a recommendation system to provide users with routes they may be interested in. This increased functionality will increase users' satisfaction with the application and could increase sales for the paid version of the app. 

### Data
The dataset contains 2,044 individual routes in the Red River Gorge area in Kentucky, along with 12 features, and 155,023 words from the routes' descriptions. Some of the features include the route's difficulty rating, length, and average user-rating. 

### Algorithms
*Feature Engineering*
1. Data Cleaning
2. Converting categorical features to binary dummy variables
3. Principal Component Analysis to decrease data to 7 features

*Text Pre-processing*
1. Remove punctuation & numbers
2. Remove stopwords
3. Convert text to lowercase
4. Lemmatize words to their roots
5. Principal Component Analysis

*Content-Based Recommendation Systems*
1. Baseline Model - Most popular routes based on weighted average user-ratings and number of ratings
2. Route Statistics Similarity Model - using pairwise distances, return n most similar routes to X, where n is the number of routes to be returned and X is the route the user inputs. The features include the numerical and categorical route data.
3. Text Based Similarity Model - using pairwise distances, return n most similar routes to X, where n is the number of routes to be returned and X is the route the user inputs. The features include the TFIDF vectors from the routes' text description.

**Final Recommendation System**
The model that returned routes that were most similar was the second model where the recommendations were based on the numerical and categorical information about the route. After reviewing the recommended routes and comparing them to the input, it was obvious that many of the features were very similar. For example: 
| Route Name                  | Difficulty | Style  | Length | Pitches | Avg. Rating |
|              :-----:        |   :----:   |  :---: |  :---: | :----:  |  :-----:    |
| Roadside Attraction (input) | 5.7        | Trad   | 20.0   | 2       | 3.7         |
| Bedtime for Bonzo           | 5.6        | Trad   | 20.0   | 2       | 3.4         |

### Tools 
* Numpy and Pandas for data manipulation
* Spacy and Scikit-learn for text processing and modeling
* Matplotlib and Seaborn for plotting

### Future Work
* Combining collaborative-based filtering with the content-based filtering for could provide a high-performing hybrid model that will produce better insights. To create that, I will be web scraping the reviews along with the users' other reviews as features for the hybrid approach. 
* Deploying an interactive application that allows for the user to input their favorite route(s) and return n recommended routes. 

### Communication
All of the slides, visuals, and coding notebooks can be found here on my Github profile. 
