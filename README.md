# Movie Recommendations

**Authors:** Alex Valencia, Mallory Wilson

## Overview
The goal of this project is to create the best movie recommendation system model for MovieLens, a movie recommendation service, so they can better predict which movies each user will want to watch next.

## Business Problem
MovieLens would like their customers to use their movie recommendation service to find movies they're most interested in watching. In order to do this, we will create the best movie recommendation system model to help predict the top ten most similar movies each user should watch based on their prior movie selections.

## Data
We examined the dataset ratings.csv on **userId**, **movieId**, and **rating**.

We examined the dataset movies.csv on **movieId** and **title**.

We examined the dataset tags.csv on **userId**, **movieId**, and **tag**.

We examined the dataset links.csv on **movieId**, **imdbId**, and **tmdbId**.

## Methods
We explored all four datasets provided to gain a better understanding of what information we were working with. After exploring all of the data, we decided to focus exclusively on the 'ratings' dataset and the 'movies' dataset. We made additional changes to the 'ratings' dataset by reshaping it in the following ways:

1. 'movieId' was set as the index.
2. 'userId' was set as the columns.
3. 'rating' was set as the values within the newly designed dataset.
4. Any ratings with a *NaN* value was changed to zero.

We filtered our datasets by counting the number of ratings each movie received, and then we kept all movies that received votes from 10 or more users.

This visualization shows the number of users who voted for each movie, and the red line represents which movies had votes from 10 or more users.

![graph1](./images/3mostcorr.png)

We filtered our datasets even more by counting the number of times a user rated a movie, and then we kept all users who had voted for 50 or more movies.

This visualization shows the number of times a user voted for a movie, and the red line represents which users voted for 50 or more movies.

![graph2](./images/Moneybywinners:nonwinnersbox.png)

We combined these two filters together and created our final dataset we used to build our recommendation system model.

Next, we inserted the ratings from our final dataset in a **CSR Matrix** because it's the best tool that helps reduce sparsity in our model. Then we took our CSR Matrix and fit it into a KNN algorithm called **NearestNeighbors**. This allowed us to select *cosine similarity* as a metric in our recommendation system model so we could find the top ten most similar movies to recommend based on what movies each user decides to watch.

## Results
After building a function for our movie recommendation system model, we were able to recommend ten movies to users based on which movie they decided to watch first.

This visualization shows the top ten movies our user should watch after selecting **A Beautiful Mind**.

![graph3](./images/Pointsbywinners:nonwinnersbox.png)

This visualization shows the top ten movies our user should watch after selecting **Star Wars**.

![graph4](./images/Pointsbywinners:nonwinnersbox.png)

This visualization shows the top ten movies our user should watch after selecting **Forrest Gump**.

![graph5](./images/Pointsbywinners:nonwinnersbox.png)

# Next Steps
One idea we would like to pursue in the future is to take all our models and combine them in a function. You would use this function to write in a name and year, and then get back a 'Yes' or 'No' based on whether or not he made enough money, fell in the correct range of points, and had a chance to be a winner. In addition, we want to expand our understanding of our **point_range** and how we can use our range to predict who would then be in the upper-quartile range in future seasons. We also want to put in a single players stats and be told by the model based on our parameters whether we should sponsor them or not. 

## Conclusions
Our recommendation system model created gave us ten movies that were the most similar to the movie chosen by the user. Our model gives an output on what movies each user will enjoy watching next. In the end, making the decision whether or not to watch a movie comes down to each user's personal preferences.

## For More Information
Please review our full analysis in [our Jupyter Notebook Money](./notebooks/report/Final_Money.ipynb), [our Jupyter Notebook Winners](./notebooks/report/final_pga_golf_data_winners.ipynb), [our Jupyter Notebook Points](./notebooks/report/Final_Points.ipynb) or our [presentation](./Golf_Sponsorship_for_our_client.pdf).

For any additional questions, please contact **Alex Valencia at asvalencia1688@gmail.com or Mallory Wilson at mallorye1103@gmail.com.**

## Repository Structure

```
├── data                                  <- data files used for analyses
├── images                                <- visualizations created
├── notebooks                             <- code written for project with explanation, as well as working ├──notebooks of members
├── Golf_Sponsorship_for_our_client.pdf   <- PDF version of powerpoint
└── README.md                             <- overview of project
```
