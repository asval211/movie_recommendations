# Movie Recommendation System Model

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

## Next Steps
One idea we would like to pursue in the future is to make a recommendation system model based on movie tags. You would use this model to figure out the correlation between tags for movies with similar tags and use that information to output movie recommendations based on how similar the tags are to each other. We used a small dataset from MovieLens to create our movie recommendation system model and we want to use a bigger dataset so we can include more movies for improved performance. Achieving this may require using a computer that can handle more storage or figuring out if there's a way to free up orage on our current computers. We also want to find the demographics of each user so we can better predict which movies they will want to watch next.

## Conclusions
Our recommendation system model created gave us ten movies that were the most similar to the movie chosen by the user. Our model gives an output on what movies each user will enjoy watching next. In the end, making the decision whether or not to watch a movie comes down to each user's personal preferences.

## For More Information
Please review our full analysis in [our Jupyter Notebook Movie Recommendation System Model](./notebooks/report/Final_Money.ipynb) or our [presentation](./Golf_Sponsorship_for_our_client.pdf).

For any additional questions, please contact **Alex Valencia at asvalencia1688@gmail.com or Mallory Wilson at mallorye1103@gmail.com.**

## Repository Structure

```
├── data                                  <- data files used for analyses
├── images                                <- visualizations created
├── notebooks                             <- code written for project with explanation, as well as working ├──notebooks of members
├── Golf_Sponsorship_for_our_client.pdf   <- PDF version of powerpoint
└── README.md                             <- overview of project
```
