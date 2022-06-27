# Business Analysis on Movie Production
![movie theatre banner](https://user-images.githubusercontent.com/95732821/175164895-ef198e07-a34c-4f8f-808a-ad6f72bb4e1a.png)

#### OVERVIEW
A MySQL database on movies was produced upon a client's request. Hypothesis testing was performed on the Movies data to give mathematically-supported answers to questions about what makes a successful movie. Then finally, the success of these movies, based on relevant features, was predicted using a Linear regression model. The data for this project, was extracted from IMDB and TMDB open source website.

- ## Phase One: IMDB Files ETL (Extract, Transform and Load) 
>
#### OBJECTIVES:

The first set of files for the movies database was extracted from a subset of IMDB's publicly available dataset. The client specified the folllowing files for the database production:

title.basics.tsv.gz
title.ratings.tsv.gz
title.akas.tsv.gz

Data Source
The dataset were obtained from the IMDB website.

Data dictionary: https://www.imdb.com/interfaces/

Data download link: https://datasets.imdbws.com/


#### RESULTS:
The files were extracted and filtered, to contain only the relevant features and enteries. The files were then converted from the initial .tsv.gz format to a csv.gz format. 

title_basics.csv.gz
title_akas.csv.gz
title_ratings.csv.gz

- ## Phase Two:  TMDB Files ETL (Extract, Transform and Load)

#### OBJECTIVES:

The files extracted in phase one were discovered to contain no financial information on movies, such as budget and revenue. In this phase, additional data was extracted from the TMDB open source website, which was recommended by the Stakeholder.

Data SOurce: (https://www.themoviedb.org/)

##### Specifications on additional data
>- Information on budget, revenue and MPAA rating (G/PG/PG-13/R), which is also called "Certification", should be extracted and added to the initial data.
>- The stakeholder is only interested in movies with the same criteria as the ones specified in the initial IMDB ETL extracted.

#### RESULTS:
Information on all the movies released between the year 2000 and the 2020 was extracted from the TMDB site. Each file wass saved as an individual .csv.gz file

- ## Phase Three: TMDB EDA (Exploratory Data Analysis)

#### OBJECTIVES:

The files obtained in the previous phase were then joined together to form a single .csv.gz file and an exploratory data analysis was performed on it.

#### RESULTS:

The answers to the following questions were obtained through the exploratory analysis.

>- How many movies are there in each of the certification categories (G/PG/PG-13/R)?

>![number of movies per certification](https://user-images.githubusercontent.com/95732821/175204204-e5159c36-0e83-4a21-a1de-4352a8b5902d.png)

> Ans: Movie with the genres: R had the highest number of 1600, followed by movies with the genre pg-13, 1400, then pg about 400. Movies with the genre Nc-17 had the lowest number of less than 50.

>- What is the average revenue per certification category?
>
>![ave rev per certification](https://user-images.githubusercontent.com/95732821/175204153-d3aeefaa-738f-4476-99d2-bffc3a6cdf27.png)

> Ans:  Movies with certifications: Pg,  and Pg-13, generated the highest average revenue of about $175,000,000 and $150,000,000 respectively, while movies with ceritification NC-17 generated the lowest average revenue of less than $25,000

>- What is the average budget per certification category?

> Ans: Movies with certification Pg had the highest average budget of about $60,000, followed by Pg-13 with about $50,000 and R had an average budget of about $45,000, while movies with certification NC-17 had the lowest budgets of less than $10,000.
![ave budget per cert](https://user-images.githubusercontent.com/95732821/175204124-39268929-d558-48b5-af9c-78f870617500.png)


- ## Phase Four: MySQL Movie DataBase ETL(Extract, Transform and Load)

#### OBJECTIVES:
This phase covers the process transforming all the IMDB and TMDB files into suitable database format and loading into a database. 

#### RESULTS

A MySQL database wass created and all the files from both IMDB and TMDB were loaded into it.


- ## Phase Five: Hypothesis Testing

#### OBJECTIVES:

This phase aimed at using hypothesis testing and statistics knowledge on the Movies Database to give mathematically-supported answers to questions about what makes a successful movie, with a backup visualization.

Null Hypothesis Theories:
>- Does the MPAA rating of a movie affect how much revenue the movie generates?

>- which rating earns the most revenue?

>- Do some movie genres earn more revenue than others?

>- Do movies that are over 2.5 hours long earn more revenue than movies that are 1.5 hours long (or less)?

>- Do movies released in 2020 earn less revenue than movies released in 2018?


#### RESULTS:

> **Hypothesis:** The MPAA rating of a movie does affect how much revenue the movie generates.

> **Findings:** Movies that have an MPAA Rating of PG, PG-13, and R generates the most revenue.

![phase_5_certification](https://user-images.githubusercontent.com/95732821/175207470-2fd544d7-d478-4d5c-9ce1-26f898dba4d8.png)

> **Hypothesis:** The genre of a movie does affect how much revenue a movie generates.

> **Findings:** Adventure, Animation, Sci-fi, fantasy, Action and family movie genres generate the greatest revenue.**

![phase_5](https://user-images.githubusercontent.com/95732821/175207482-f69b4604-fa96-4948-82ad-b669a7c42438.png)

> **Hypothesis:** Do movies that are over 2.5 hours long earn more revenue than movies that are 1.5 hours long (or less)?

> **Findings:** Movies that are over 2.5 hours have a significantly different revenue than movies that under 1.5 hours in length.**

![phase_55](https://user-images.githubusercontent.com/95732821/175207441-325aa117-bcb1-4145-a4be-cb29d35ca05d.png)

> **Hypothesis:** Do movies released in 2020 earn less revenue than movies released in 2018?
> 
> **Findings:** There is a significant difference in the revenue of movies released in the year 2018 and those released in the year 2020. The revenue of movies released in 2020 is much lower than that of the year 2018, this can be attributed to the covid 19 pandemic.

![phase_5555](https://user-images.githubusercontent.com/95732821/175207420-e0524641-913c-4bb2-a483-6fa01d9388be.png)


- ## Phase Six: Linear Regression Prediction of a Successful Movie

#### OBJECTIVES:

A linear regression model is to be built with all four assumptions of linear regression being put into consideration. The model is to predict the success(revenue) of a movie using the features being filtered when tuning the model to meet the four assumptions of linear regression. The four assumptions are as follows:

>>- Normality: The model's residuals are approximately normally distributed.

>>- Homoscedasticity: The model residuals have equal variance across all predictions.

>>- Linearity: That the input features have a linear relationship with the target.

>>- Independence of features (AKA Little-to-No Multicollinearity): That the features are not strongly related to other features.

#### RESULTS:

The four assumptions of linearity were met after dropping some of the features such as outliers, features that are highly correlated, features that do not have linearity with the target(revenue), and features with high p-values. The model was trained based on the remaining features and the resulting r2 score is a s follows:

Training R^2: 0.770
Testing  R^2: 0.737


# Summary 
Datasets on movie production were extracted from the IMDB and TMDB open source website. The files were cleaned, and transformed into a suitable format. A MySQL data base was created and the files were saved into tables in the database. The data was then being analysed and certain hypothesis theories were supported statistically. A linear gression model was then built to predict the success of moies based on the filtered features after meeting the four assumptions of linearity.
# Recommendations

In order to maximize revenue for a movie, it is be recommended to produce, a movie with the following genres: PG rated, adventure, animation,fantasy or scifi movie and a  movie runtime greater than 2.5 hours. When it comes to predicting the success of the movie however a linear regression model might not be the best model for predicting the success of movies, that is because the linear regression model is not smart enough to consider those factors that do not have linear relations with the target vector, when infact these features are relevant towards predicting the success of a movie. A more sophisticated machine learning model such as Random Forest regressor, would dp a much better job.
