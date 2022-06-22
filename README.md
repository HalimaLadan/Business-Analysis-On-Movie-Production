# Business Analysis on Movie Production
![movie theatre banner](https://user-images.githubusercontent.com/95732821/175164895-ef198e07-a34c-4f8f-808a-ad6f72bb4e1a.png)

"C:\Users\heill\Downloads\movie theatre banner.png"
A client has requested the production of a MySQL database on movies. A hypothesis testing is to be performed on the Movies Database to give mathematically-supported answers to questions about what makes a successful movie. Then finally and a Linear regression model that can predict the success of movies based on relevant features is to be built. The data for this project, is to be extracted from IMDB and TMDB open source website.
>- ## Phase One: IMDB Files ETL (Extract, Transform and Load)
 
#### OBJECTIVES:

A client has requested the production of a MySQL database on movies. The dataset is to be extracted from a subset of IMDB's publicly available dataset. The client specified the folllowing files for the database production:

title.basics.tsv.gz
title.ratings.tsv.gz
title.akas.tsv.gz
An indepth analysis is to be performed on the dataset and the factors that makes a movie successfull is to be recommended.

Data Source
The dataset were obtained from the IMDB website.

Data dictionary: https://www.imdb.com/interfaces/

Data download link: https://datasets.imdbws.com/


#### RESULTS:

Movie-Production-Business-Analysis repository
title_basics.csv.gz
title_akas.csv.gz
title_ratings.csv.gz

>- ## Phase Two:  TMDB Files ETL (Extract, Transform and Load)

#### OBJECTIVES:

Previously in phase one, a set of data was gotten from the IMDB for analyzing the success of movies, but it was discovered that the dataset contained no financial information on the movies(Budget or Revenue). In order for the movies to be analyzed , additional data on the financial is required. The business stakeholder, identified The Movie Database (TMDB) as a great source of additional financial data

Data SOurce: (https://www.themoviedb.org/)

Data Specifications
information on budget, revenue and MPAA rating (G/PG/PG-13/R), which is also called "Certification", should be extracted and added to the initial data.
The stakeholder is only interested in movies with the same criteria as the ones specified in the initial IMDB ETL extracted.

#### RESULTS:
final_tmdb_data_2000.csv.gz
final_tmdb_data_2001.csv.gz
tmdb_results_combined.csv.gz


>- ## Phase Three: TMDB EDA (Exploratory Data Analysis)

#### OBJECTIVES:

The Data gotten from the previously combined TMDB files in phase two would be analysed and the answer to the following questions found through exploratory data analysis.( Exclude any movies with null values and 0's for budget AND revenue from the remaining visualizations.)

>- How many movies had at least some valid financial information (values > 0 for budget OR revenue)?
>- How many movies are there in each of the certification categories (G/PG/PG-13/R)?
>- What is the average revenue per certification category?
>- What is the average budget per certification category?

"C:\Users\heill\OneDrive\Desktop\ave budget per cert.png"
"C:\Users\heill\OneDrive\Desktop\ave budget per cert.png"
"C:\Users\heill\OneDrive\Desktop\ave rev per certification.png"
"C:\Users\heill\OneDrive\Desktop\number of movies per certification.png"


#### RESULTS:

SQL "Movies" database with the following tables:

title_basics
title_ratings
title_genres
genres
tmdb_data

>- ## Phase Four: MySQL Movie DataBase ETL(Extract, Transform and Load)

#### OBJECTIVES:
This phase covers the process converting all the IMDB and TMDB files into suitable format for the database. A MySQL database would be created and all the files will be loaded into it.

#### RESULTS

final_tmdb_data_2000.csv.gz
...
final_tmdb_data_2021.csv.gz
tmdb_results_combined_final_df.csv.gz
Phase 4 - Hypothesis Testing

>- ## Phase Five: Hypothesis Testing

#### OBJECTIVES:
This phase covers the use of hypothesis testing and statistics knowledge on the Movies Database to give mathematically-supported answers to questions about what makes a successful movie, with a backup visualization.

Question 1:
Does the MPAA rating of a movie affect how much revenue the movie generates?

If so, what was the p-value of the analysis?

And which rating earns the most revenue?

Question 2:
Do some movie genres earn more revenue than others?
Question 3:
Do movies that are over 2.5 hours long earn more revenue than movies that are 1.5 hours long (or less)?
Question 4:
4A
 - Do movies released in 2020 earn less revenue than movies released in 2018?
4B
How do the years compare for movie ratings?


"C:\Users\heill\OneDrive\Desktop\phase_5.png"
"C:\Users\heill\OneDrive\Desktop\phase_5_certification.png"
"C:\Users\heill\OneDrive\Desktop\phase_55.png"
"C:\Users\heill\OneDrive\Desktop\phase_5555.png"
"C:\Users\heill\OneDrive\Desktop\phase_555555.png"
"C:\Users\heill\OneDrive\Desktop\555.png"

#### RESULTS:
The MPAA rating of a movie does affect how much revenue the movie generates.
Movies that have an MPAA Rating of PG make the most revenue.
The genre of a movie does affect how much revenue a movie generates.
Adventure, Sci-fi, and Action movie genres, in descending order generate the greatest revenue.
Movies that are over 2.5 hours have a significantly different revenue than movies that under 1.5 hours in length.

>- ## Phase Six: Linear Regression Prediction of a Successful Movie
#### OBJECTIVES:
A linear regression model is to be built with all four assumptions of linear regression being put into consideration. The model is to predict the success(revenue) of a movie using the features being filtered when tuning the model to meet the four assumptions of linear regression. The four assumptions are as follows:

>>- Normality: The model's residuals are approximately normally distributed.

>>- Homoscedasticity: The model residuals have equal variance across all predictions.

>>- Linearity: That the input features have a linear relationship with the target.

>>- Independence of features (AKA Little-to-No Multicollinearity): That the features are not strongly related to other features.

#### RESULTS:
"C:\Users\heill\OneDrive\Desktop\snip.png"
"C:\Users\heill\OneDrive\Desktop\snip.png"
"C:\Users\heill\OneDrive\Desktop\lin2.png"

# Summary 

The MPAA rating of a movie does affect how much revenue the movie generates.
Movies that have an MPAA Rating of PG make the most revenue.
The genre of a movie does affect how much revenue a movie generates.
Adventure, Sci-fi, and Action movie genres, in descending order generate the greatest revenue.
Movies that are over 2.5 hours have a significantly different revenue than movies that under 1.5 hours in length.

# Recommendations

In order to maximize revenue for a movie, it would be recommended to produce:

A PG rated, adventure, animation,fantasy or scifi movie with a runtime greater than 2.5 hours.
