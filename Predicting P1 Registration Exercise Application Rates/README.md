# Capstone Project: Predicting Primary Schools Application Rate
---
## Background

Many Singaporean parents go to great lengths to help secure a place in the primary school of their choice as they want to give their children the best start to their formal schooling years.

In order to have a higher chance of getting into their coveted school, many of them move closer to the school of their choice so that they can be within the school’s 1-2km radius.

However, there is an increasing trend of balloting for children staying within 1km of the school at Phase 2C. Phase 2C is the phase where priority is distance-based, given to Singaporeans living within 1km of the school.

## Problem Statement

The annual Pri 1 registration exercise has morphed into a complicated scheme comprising six phases involving different priority rules. 

We want to help parents make better decisions by using machine learning to predict the application rates for each school at each phase for subsequent years. This will help parents decide whether it is worth it to move closer or be a parent volunteer at the school of their choice.

The goal of the project will be to use machine learning to predict the application rate of schools for next 2 years and achieve R-Squared > 0.70 for majority of the predictions.

## Data Collection

The data was scraped using BeautifulSoup from Sgschooling.com, a website that collates every primary school’s balloting history. 

The scraped dataset shows the number of applicants and number of vacancies for each school, split into 7 different application phases. We ran a loop to obtain the data from the years 2009 to 2022.


## Data Cleaning and Preprocessing

We have input missing values using Regex and by subtracting from other variables.

We have combined Phase 2A(1) and Phase 2A(2) into Phase 2A to be aligned with latest 2022 changes

The columns and rows were rearranged to a neater form for the ease of running the prediction model.

We have input the full name of school as the original data was using the short form.

We created a new column 'Application Rate' by dividing 'Applied' over 'Vacancy' and this will be the target variable that we will be predicting.

## Modelling

Phase 2C(S) and Phase 3 columns were dropped as these phases are not as competitive as previous phases. We will run predictions only for the competitive phases. The clean dataset used for modelling consists of 10044 rows

We used Facebook’s Prophet to predict the application rate at each phase for each school for the next 3 years. 

As there is a large number of models to be run (186 schools x 4 phases), it is not possible to get high accuracy for all using the same parameters. We used moving average instead of raw data to achieve higher accuracy.

The first model was run using 3-day moving average and we filtered out rows with R-Squared > 0.7. Then we ran the second model with remaining rows using 3-day moving average with parameter changepoint_prior_scale=0.3 and filtered out rows with R-Squared > 0.7. After that, we ran the third model with remaining rows using 2-day moving average

## Model Evaluation

After 3 rounds of modeling, 86.7% of the predictions have an R-Squared of more than 0.7. A total of 724 predictions were made.

## Limitations and Future Plans
R-Squared can be further improved for the remaining predictions with R-Squared < 0.7. We can further tune the hyperparameters and run the model a few more times to obtain higher accuracy

There was a major policy change in 2022 where Phases 2A(1) and 2A(2) were combined and there were higher number of vacancies allocated for Phase 2C. The current predictions may not be as accurate as there is only 1 year of data with this new policy change effected. As we collect more data over the next few years, we foresee that the accuracy of predictions will improve.

## Conclusion

We managed to meet our objective of using machine learning to predict future application rates with R-Squared > 0.7 for majority of the predictions (86.7% of the predictions).

Parents can refer to the balloting history and application rate predictions of the school to see if there is a high chance of balloting within 1km. If the competition for space at the school is too stiff i.e. very high predicted application rate, there is a high chance of balloting within 1km and it will not be recommended for parents to specially move near the school of their choice.