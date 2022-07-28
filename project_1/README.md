# Project 1: Standardized Test Analysis

## Problem Statement
Due to the Covid-19 pandemic, many colleges and universities in the US have switched to a test-optional policy in regard to SAT and ACT score submission. We would like to know if it is still important for students to submit their SAT and ACT scores even when tests are optional for most schools. 

We also want to understand if there is a relationship between the scores and the college acceptance rate. 

Lastly, we want to find out what SAT and ACT scores students should aim for in order to enter their dream schools.


## Data Dictionary


|Feature|Type|Dataset|Description|
|---|---|---|---|
|intended_college_major|object|sat_2019_by_intended_college_major.csv|Major which students intend to take in college| 
|num_test_takers|int|sat_2019_by_intended_college_major.csv|Number of test takers for each intended college major| 
|percentage_of_majors|float|sat_2019_by_intended_college_major.csv|Percentage of test takers for each intended college major| 
|total_score|int|sat_2019_by_intended_college_major.csv|Mean combined SAT reading, writing and math score| 
|reading_writing|int|sat_2019_by_intended_college_major.csv|Mean SAT reading and writing score| 
|math|int|sat_2019_by_intended_college_major.csv|Mean SAT math score| 
|school|object|sat_act_by_college.csv|College or university| 
|are_test_optional|object|sat_act_by_college.csv|Whether SAT or ACT tests are optional in the college| 
|class_year|object|sat_act_by_college.csv|The year of the test optional policy| 
|policy_details|object|sat_act_by_college.csv|Details of the test optional policy| 
|num_of_applicants|int|sat_act_by_college.csv|Number of applicants to each college or university| 
|acceptance_rate|float|sat_act_by_college.csv|Percentage of the applicants who were accepted to the school| 
|sat_middle_range|float|sat_act_by_college.csv|Range of 25th to 75th percentile of SAT score for applicants to the school| 
|act_middle_range|float|sat_act_by_college.csv|Range of 25th to 75th percentile of ACT score for applicants to the school| 
|sat_25th_percentile|float|sat_act_by_college.csv|25th percentile of SAT score for applicants to the school| 
|sat_75th_percentile|float|sat_act_by_college.csv|75th percentile of SAT score for applicants to the school| 
|act_25th_percentile|float|sat_act_by_college.csv|25th percentile of ACT score for applicants to the school| 
|act_75th_percentile|float|sat_act_by_college.csv|75th percentile of ACT score for applicants to the school| 

## Conclusions/Recommendations

Most colleges and universities have adopted test-optional policies and only around 6% of schools have mandatory SAT and ACT scores requirements.

However, SAT and ACT scores still play an important role for college admissions especially for top schools with very low acceptance rates and for popular STEM related majors. There is a strong negative correlation between the college acceptance rate and SAT and ACT scores i.e. the lower the college acceptance rate, the higher the SAT and ACT scores of students.

It might be beneficial for students to take the tests and then decide whether to submit their scores by comparing against that the score range of the school.

Students should target for the 75th percentile of the SAT and ACT score of the school which they wish to enter for higher chances of college acceptance.