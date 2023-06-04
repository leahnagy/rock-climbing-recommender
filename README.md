# Natural Language Processing (NLP) Project 
## Rock Climbing Route Recommender
Created By: Leah Nagy

### Contents
1. [Presentation Slides](https://github.com/leahnagy/rock-climbing-recommender/blob/main/slides.pdf) 
2. [Webscraping Scripts](https://github.com/leahnagy/rock-climbing-recommender/blob/main/code_webscrape_routes.ipynb)
3. [Project Scripts](https://github.com/leahnagy/rock-climbing-recommender/blob/main/code_recommendations.ipynb)

### Project Description
This project set out to develop a system that could suggest similar rock climbing routes based on a user-specified input. The data was gathered from Mountain Project's website, which encompasses statistics, location, and textual descriptions of each route. By applying feature engineering and pairwise distance metrics, the system was designed to return the most analogous routes, given a particular input route. 

### Project Design
Mountain Project is a popular platform where rock climbers find information about different routes globally. However, it lacks a recommendation system that could potentially enhance user experience and drive sales of the app's premium version. This project aims to bridge this gap by introducing a recommendation system tailored to individual users' preferences.

### Dataset
The dataset comprises 2,044 unique climbing routes located in the Red River Gorge area in Kentucky. Each route is characterized by 12 features and described with a corpus of 155,023 words. Features include the difficulty level of the route, its length, and the average user rating.

### Methodology

*Feature Engineering*
1. Data Cleaning
2. Transformation of categorical features into binary dummy variables
3. Reduction of data dimensions to 7 features via Principal Component Analysis

*Text Pre-processing*
1. Removal of punctuation & numeric characters
2. Elimination of stopwords
3. Conversion of text to lowercase
4. Lemmatization to simplify words to their root form
5. Dimension reduction via Principal Component Analysis

*Content-Based Recommendation Systems*
1. Baseline Model - Offers popular routes based on weighted average user-ratings and the number of ratings
2. Route Statistics Similarity Model - Utilizes pairwise distances to suggest the n most similar routes to X (where n is the number of desired route recommendations, and X is the user's input route). Features comprise numerical and categorical route data.
3. Text Based Similarity Model - Works similarly to the previous model but uses TFIDF vectors derived from route descriptions.

The model offering the most coherent recommendations was the Route Statistics Similarity Model, which bases its suggestions on the numerical and categorical information about the route. A cursory comparison of the recommended routes with the input route indicated considerable feature similarity.

### Tools Utilized
* Data manipulation: Numpy and Pandas
* Text processing and modeling: Spacy and Scikit-learn
* Plotting: Matplotlib and Seaborn

### Future Enhancements
* The inclusion of collaborative-based filtering with the current content-based filtering could create a hybrid model that yields improved recommendations. This would necessitate web scraping user reviews and employing them as features for the hybrid model.
* Deployment of an interactive application that allows users to input their favorite routes and receive n recommended routes.
